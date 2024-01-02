<script lang="ts">
import {defineComponent} from "vue";
import {data} from "autoprefixer";

export default defineComponent({
  mounted() {
    this.fetchWeather();
  },
  methods: {
    async fetchWeather(){
      const apiKey = 'e30b514a95528199c857c8b33d8ed21d';
      const response = await fetch(`https://api.openweathermap.org/data/3.0/onecall?lat=43.76&lon=-79.41&units=metric&appid=${apiKey}`);
      const data = await response.json();
      console.log(data);
      this.temperature = parseFloat((data.current.temp).toFixed(2));
      this.highest = parseFloat((data.daily[0].temp.max).toFixed(2));
      this.lowest = parseFloat((data.daily[0].temp.min).toFixed(2));
      this.daily = data.daily;
      this.minutes = data.minutely;
      this.hours = data.hourly;
    }
  },
  data() {
    return {
      city: 'North York',
      temperature: 7.14,
      highest:10,
      lowest:1,
      sunrise:10,
      sunset:20,
      daily:undefined,
      minutes:undefined,
      hours:undefined
    };
  }
});
</script>

<script setup lang="ts">


</script>

<template>
  <header>
  </header>
  <main>
    <div class="bg-gradient-to-b from-[#87CEEB] to-[#E3E2DF] min-h-screen">
      <div class="text-light-greenish-yellow-darker">
      <h1 class="font-pixel text-6xl text-center">Today's weather</h1>
      <p  class="font-pixel text-4xl text-left">location : <span class="font-pixel text-4xl text-red-500">{{city}}</span></p>
        <p class="font-pixel text-4xl text-left">Temperature : <span class="font-pixel text-4xl ">{{temperature}}</span></p>
        <p  class="font-pixel text-4xl text-left">highest : <span class="font-pixel text-4xl ">{{highest}}</span></p>
        <p  class="font-pixel text-4xl text-left">lowest : <span class="font-pixel text-4xl ">{{lowest}}</span></p>
        <p  class="font-pixel text-4xl text-left">sunrise : <span class="font-pixel text-4xl ">{{sunrise}}</span></p>
        <p  class="font-pixel text-4xl text-left">sunset : <span class="font-pixel text-4xl">{{sunset}}</span></p>
        <p  class="font-pixel text-4xl text-left">hourly : <span class="font-pixel text-4xl">{{sunset}}</span></p>
        <div class="font-pixel text-4xl text-left flex flex-row">
          <div class="basis-1/4">
            <p  v-if="hours" class="font-pixel text-4xl text-left">This hour : <span class="font-pixel text-4xl">{{hours[0].temp}}</span></p>
            <p  v-if="minutes" class="font-pixel text-3xl text-left">minutes : <span class="font-pixel text-4xl">{{minutes[0].precipitation}}</span></p>
          </div>
          <div class="basis-1/4">
            <p  v-if="hours" class="font-pixel text-4xl text-left">Next hour : <span class="font-pixel text-4xl">{{hours[1].temp}}</span></p>
          </div>
          <div class="basis-1/4">
            <p  v-if="hours" class="font-pixel text-4xl text-left">2 hour : <span class="font-pixel text-4xl">{{hours[2].temp}}</span></p>
          </div>
          <div class="basis-1/4">
            <p  v-if="hours" class="font-pixel text-4xl text-left">3 hour : <span class="font-pixel text-4xl">{{hours[3].temp}}</span></p>
          </div>
        </div>

      <h2 class="font-pixel text-4xl text-left">Daily : </h2>
        <div class="flex flex-row">
          <div class="flex flex-col basis-1/4">
            <p class="text-light-greenish-yellow-darker font-pixel text-4xl text-left">Today</p>
            <p v-if="daily" class="font-pixel text-4xl text-left"><span class="font-pixel text-4xl text-red-500">{{daily[0].summary}}</span></p>
          </div>
          <div class="flex flex-col basis-1/4">
            <p class="text-light-greenish-yellow-darker font-pixel text-4xl text-left">Tomorrow</p>
            <p v-if="daily" class="font-pixel text-4xl text-left"><span class="font-pixel text-4xl text-red-500">{{daily[1].summary}}</span></p>
          </div>
          <div class="flex flex-col basis-1/4">
            <p class="text-light-greenish-yellow-darker font-pixel text-4xl text-left">ThirdDay</p>
            <p v-if="daily" class="font-pixel text-4xl text-left"><span class="font-pixel text-4xl text-red-500">{{daily[2].summary}}</span></p>
          </div>
          <div class="flex flex-col basis-1/4">
            <p class="text-light-greenish-yellow-darker font-pixel text-4xl text-left">ForthDay</p>
            <p v-if="daily" class="font-pixel text-4xl text-left"><span class="font-pixel text-4xl text-red-500">{{daily[3].summary}}</span></p>
          </div>
        </div>
      </div>
<!--      <img src="../resources/images/sun.png">-->
<!--      <img src="../resources/images/cloudy.png">-->
<!--      <img src="../resources/images/most_cloudy.png">-->
<!--      <img src="../resources/images/rain.png">-->
<!--      <img src="../resources/images/snow.png">-->
    </div>
  </main>
</template>

<style scoped>
@media screen {
  height:100vh;
}
@font-face {
  font-family: Pixel;
  src: url('../resources/font/EnterCommand.ttf')format('truetype');
  font-weight: normal;
  font-style: normal;
}
span{
  color: #eb87ce;
}
</style>