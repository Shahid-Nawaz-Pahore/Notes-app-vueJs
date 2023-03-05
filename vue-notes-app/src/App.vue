<script setup>
import {ref} from 'vue';
const showModal = ref(false);
//define state of newnotes
const newNote = ref("");
const errorMassage = ref("");
const notes = ref([])

function getRandomColor() {
  return  "hsl(" + Math.random() * 360 + ", 100%, 75%)";
  
}
const addNote = ()=>{
  if(newNote.value.length < 10){
    return errorMassage.value ="Please Add more than 10 character in notes";
  }
  notes.value.push({
    id:Math.floor(Math.random()*10000),
    Text:newNote.value,
    date:new Date(),
    background_color:getRandomColor(),
  })
  showModal.value = false,
  newNote.value = ""
  errorMassage.value=""
}
</script>
<template>
  <main>
  
     <div v-if="showModal" class="overlay">
      
      <div class="model">
      
        <textarea v-model.trim="newNote" name="note" id="note" cols="3 0" rows="10"></textarea>
        <p v-if="errorMassage">{{ errorMassage }}</p>
         <button @click="addNote()">Add Notes</button>
         <button @click="showModal=false" class="close">Close</button>
      </div>
    </div> 
    <div class="container">
      <header>
        <h1>Notes</h1>
        <button @click="showModal=true">+</button>
      </header>
      <div class="cards-container">
        <div v-for="note in notes" :key="note.id" class="card" :style="{backgroundColor:note.background_color}">
          <p class="main-text">{{ note.Text }}</p>
          <p class="date">{{ note.date.toLocaleDateString("en-US") }}</p>
        </div>
      </div>
     
    </div>
  
  </main>
</template>
<style scoped>
main{
  height: 100vh;
  width: 100vw;
}
.container{
  max-width: 1000px;
  padding: 10px;
  margin: 0 auto;
}
header{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
h1{
  font-weight: bold;
  margin-bottom: 25px;
  font-size: 75px;
}
header button{
  background: none;
  padding: 10px;
  width: 50px;
  height: 50px;
  cursor: pointer;
  background-color: rgb(59, 46, 46);
  border-radius: 100%;
  color: white;
  font-size: 20px;
}
.card{
  width: 225px;
  height: 225px;
  background-color: rgb(148, 19, 19);
  padding: 10px;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-right: 20px;
  margin-bottom: 20px ;
}
date{
  font-size: 12px;
  font-weight: bold;
}
.cards-container{
  display: flex;
  flex-wrap: wrap;
}
.overlay{
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: rgb(0,0,0,0,77);
  z-index: 10;
  display: flex;
  align-items: center;
  justify-content: center;
}
.model{
  width: 750px;
  background-color: white;
  border-radius: 10px;
  padding: 30px;
  position: relative;
  display: flex;
  flex-direction: column;

}
.model button{
  padding: 10px 20px;
  font-size: 20px;
  width: 100%;
  background-color: blueviolet;
  border: none;
  color: white;
  cursor: pointer;
  margin-top: 15px;
  
}
.model .close{
  background-color: rgb(125, 17, 17);
  margin-top: 7px;
}
.model p{
  color: red;
}

</style> 