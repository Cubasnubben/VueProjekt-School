<script setup>
import {useRoute} from "vue-router"
import {ref, onBeforeMount} from "vue"
import bands from "../band.json"


const band = ref(null)
const route = useRoute()
const {id} = route.params;
onBeforeMount(() => {
band.value = bands.find(i => i.id === (id))
})

</script>


<template>
    <div class="container">
<div v-if="band">
     <h1>BAND INFO</h1>
<div class="card">
    <img src="../assets/pics/korn.jpg" alt="korn">


     <h2> <span>NAMN:</span> {{band.name}}</h2>
     <h2> <span>GENRE:</span> {{band.genre}}</h2>
     <h2> <span>FOUND:</span> {{band.geo}}</h2>
     <h2> <span>BUILD:</span> {{band.years}}</h2>
     <h2> <span>MEMBERS:</span> {{band.members}}</h2>
    </div>
</div>
<div v-else>
    <h1><span>404</span> Page Not Found</h1>
</div>

    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Special+Elite&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Genos&display=swap');
span{
    color: black;
    font-weight: bolder;

}
.card{
        padding: 10px;
        width: 1200px;
        margin-right: 35px;
        margin-bottom: 35px;
        box-shadow: 1px 1px 8px rgba(0, 0, 0, 0.348);
        background-color: #caced1;
        color: black;
        border-radius: 10px;
        /* text-align: center; */
}
img{
    display: flex;
    align-items: flex-end;
    width: 200px;
    height: 200px;
}



h1{
    text-align: center;
    font-size: 70px;
    font-family: 'Special Elite', cursive;
}
h2{
    font-family: 'Genos', sans-serif;
}
</style>
