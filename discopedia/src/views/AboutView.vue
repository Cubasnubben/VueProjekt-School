<script setup>
</script>

<template>
<main class="container">
  <div class="pics">
  <img src="../assets/pics/chevelle.jpg" alt="chevelle">
  <img src="../assets/pics/inflames.jpg" alt="chevelle">
  <img src="../assets/pics/onesidezero.jpg" alt="chevelle">
  <img src="../assets/pics/tool.jpg" alt="chevelle">
  <img src="../assets/pics/soen.jpg" alt="chevelle">

  </div>
  <div class="card">
    <h1>DISCOPEDIA 2023</h1>
    <p>Discopedia är en Bandinformationssida utvecklad för information om bands historia, turnédatum, bokning etc</p>
  </div>

</main>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Special+Elite&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Fredericka+the+Great&display=swap');

h1{
  font-family: 'Fredericka the Great', cursive;
  font-size: 90px;
}
p{
  background-color: rgb(255, 255, 255);
  padding:  100px;
  margin: 20px auto;
  width: 900px;
  font-size: 30px;
  font-family: 'Special Elite', cursive;
  border-radius: 40px;
}
.card {
  padding: 10px;
  width: 1200px;
  margin-right: 35px;
  margin-bottom: 35px;
  box-shadow: 2px 2px 8px rgba(0, 0, 0, 0.348);
  background-color: #caced1;
  color: black;
  border-radius: 10px;
  text-align: center;
}
.pics{
  display: flex;
  margin: 5px;
  padding: 5px;

}
img{
  margin: 5px;
  border-radius: 10px;
}

@media all and (max-width:470px) {
  .pics {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  h1{
font-size: 30px;
}
p{
  width: min-content;
}

}
</style>
