<script setup>
import { RouterView } from 'vue-router'
import bandData from "../band.json"
//för uppdatering av jsonfil
import { ref } from "vue"



const bands = ref(bandData)

</script>

<template>

  <main class="container">


    <div class="cards">
      <div v-for="band in bands" :key="band.id" class="card">
        <h1>{{ band.name }}</h1>
        <h3>{{ band.geo }}</h3>
        <h5>{{ band.genre }}</h5>
      </div>
    </div>

  </main>
  <RouterView />
</template>



<style scoped>
.cards {
  display: flex;
  width: 1400px;
  flex-wrap: wrap;
  margin-top: 50px;
  justify-content: center;
}

.card {
  padding: 10px;
  width: 350px;
  margin-right: 35px;
  cursor: pointer;
  margin-bottom: 35px;
  box-shadow: 1px 1px 8px rgba(0, 0, 0, 0.348);
  background-image: url(../assets/pics/katatonia.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  color: rgb(255, 255, 255);
}
h1 {
  font-family: 'Rubik Vinyl', cursive;
  color: rgb(246, 181, 181);
  font-weight: bolder;
}
</style>
