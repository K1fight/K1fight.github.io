<script setup>
import eclass from '../components/eclass.vue'
import weather from '../components/weather.vue'
import yorkEmail from '../components/yorkEmail.vue'
import 'tailwindcss/tailwind.css'
import './globals.css'
</script>

<template>
  <header>



  </header>
  <!--class="flex text-center divide-x-4 divide-solid divide-blue-500 min-h-screen"-->
  <main>
  <div class="min-h-screen">
    <weather/>
  </div>
<!--  <div class="flex-1 w-1/3">-->
<!--    <york-email/>-->
<!--  </div>-->
<!--  <div class="flex-1 w-1/3">-->
<!--    <eclass/>-->
<!--  </div>-->

  </main>
</template>

<style scoped>
</style>
