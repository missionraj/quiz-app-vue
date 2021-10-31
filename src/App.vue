<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import Quiz from "@/components/Quiz.vue"
</script>

<template>
  <div class="container">
    <Quiz />
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Merriweather:ital@0;1&family=Mukta&family=Roboto+Slab&display=swap');


*{
  box-sizing: border-box;
}
body { 
  margin:0;
  font-family: 'Merriweather', serif;
  font-family: 'Mukta', sans-serif;
  font-family: 'Roboto Slab', serif;
}
.container { 
  background: #8e9eab;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #eef2f3, #8e9eab);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #eef2f3, #8e9eab); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

  height: 100vh;

  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
