<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  data() {
    return {
      city: 'North York',
      temperature: 7.14,
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
    <h1 class="font-bold font-serif text-3xl">Weather</h1>
    <h2 class="font-bold font-serif text-left">Temperature<span class="text-2xl text-red-500">{{temperature}}</span></h2>
    <p  class="text-left">highest:</p>
    <p>location:{{city}}</p>
  </main>
</template>

<style scoped>
@media screen {
  height: 100vh;
}
</style>