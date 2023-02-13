<script setup>
import { RouterView } from 'vue-router'
import bandData from "./band.json"
//för uppdatering av jsonfil
import {ref} from "vue"
import Navbar from "./components/NavBar.vue"


const bands = ref(bandData)

</script>

<template>
<main class="container">
<Navbar />

  <div class="cards">
    <div v-for="band in bands"  class="card">
<h1>{{ band.name }}</h1>
<h5>{{ band.geo }}</h5>
<p>{{ band.members.drums }}</p>
    </div>
  </div>
</main>

  <RouterView />
</template>

<style scoped>

</style>
