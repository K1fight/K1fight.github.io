<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  data() {
    return {
      city: 'North York',
      temperature: 7.14,
      highest:10,
      lowest:1,
      daily:10
    };
  }
  // mounted() {
  //   this.fetchWeather();
  // },
  // methods: {
  //   async fetchWeather(){
  //     const apiKey = 'e30b514a95528199c857c8b33d8ed21d';
  //     const response = await fetch(`https://api.openweathermap.org/data/3.0/onecall?lat=43.76&lon=-79.41&appid=${apiKey}`);
  //     const data = await response.json();
  //     console.log(data);
  //     const tempInKelvin = data.current.temp;
  //     this.temperature = parseFloat((tempInKelvin - 273.15).toFixed(2));
  //     this.highest = parseFloat((data.daily[0].temp.max-273.15).toFixed(2));
  //     this.lowest = parseFloat((data.daily[0].temp.min-273.15).toFixed(2));
  //     this.daily = data.daily;
  //   }
  // }
});
</script>

<script setup lang="ts">


</script>

<template>
  <header>
  </header>
  <main>
    <div class="bg-gradient-to-b from-[#87CEEB] to-[#00BFFF] min-h-screen">
      <h1 class="font-pixel text-6xl text-left">Today's weather:</h1>
      <h2 class="font-pixel text-4xl text-left">Temperature : <span class="font-pixel text-4xl text-red-500">{{temperature}}</span></h2>
      <p  class="font-pixel text-4xl text-left">highest : <span class="font-pixel text-4xl text-red-500">{{highest}}</span></p>
      <p  class="font-pixel text-4xl text-left">lowest : <span class="font-pixel text-4xl text-red-500">{{lowest}}</span></p>
      <p  class="font-pixel text-4xl text-left">location : <span class="font-pixel text-4xl text-red-500">{{city}}</span></p>
      <h2 class="font-pixel text-4xl text-left">Daily : <span class="font-pixel text-4xl text-red-500">{{daily}}</span></h2>
      <img src="../resources/images/sun.png">
      <img src="../resources/images/cloudy.png">
      <img src="../resources/images/most_cloudy.png">
      <img src="../resources/images/rain.png">
      <img src="../resources/images/snow.png">
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
</style>