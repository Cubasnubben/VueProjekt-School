<script setup>

import bandData from "../band.json"
//för uppdatering av jsonfil
import { ref, watch } from "vue"
import {useRouter} from "vue-router"

const router = useRouter()

const bands = ref(bandData)
const genre = ref("")

watch(genre, () => {
  if(genre.value){
    if(genre.value === "Alla") return bands.value = bandData;
    else{
      bands.value = bandData.filter(b => b.genre === genre.value)
    }
  }
})
</script>




<template>
  <h2>SÖK GENOM KATEGORI</h2>
  <div class="bandsearch">
    <select v-model="genre">
      <option value="Alla">Alla</option>
      <option value="Nu Metal">Nu Metal</option>
      <option value="Hardcore">Hardcore</option>
      <option value="Groove Metal">Groove Metal</option>
      <option value="Death Metal">Death Metal</option>
      <option value="Progressive Metal">Progressive Metal</option>
      <option value="Alternativ Rock">Alternativ Rock</option>
      <option value="Heavy Melodic Rock">Heavy Melodic Rock</option>
    </select>
  </div>



  <main class="container">


    <div class="cards">
      <div v-for="band in bands" :key="band.id" class="card" @click="router.push(`/band${band.id}`)">
        <h1>{{ band.name }}</h1>
      </div>
    </div>

  </main>
  <!-- <RouterView /> -->
</template>



<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Special+Elite&display=swap');
.cards {
  display: flex;
  width: 1400px;
  flex-wrap: wrap;
  margin-top: 50px;
  justify-content: center;
}

.card {
  padding: 10px;
  width: 500px;
  margin-right: 35px;
  cursor: pointer;
  margin-bottom: 35px;
  box-shadow: 1px 1px 8px rgba(0, 0, 0, 0.348);
  background-image: url(../assets/pics/katatonia.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  color: rgb(255, 255, 255);
  border-radius: 10px;
}
h1 {
  font-family: 'Rubik Vinyl', cursive;
  color: rgb(255, 255, 255);
  font-weight: bolder;
  text-align: center;;
}

.bandsearch{
display: flex;
justify-content: center;
}
h2{
  text-align: center;
  font-family: 'Special Elite', cursive;
}
option{
  font-family: 'Special Elite', cursive;
}

@media all and (max-width: 470px){

}
</style>
