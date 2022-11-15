<script setup>
  import {ref} from "vue"

  const showModal = ref(false)

  const newNote = ref("")

  const notes = ref([])

  const errorMessage = ref("")

  function getRandomColor(){
    return 'hsla(' + (Math.random() * 360) + ', 100%, 50%, 1)';
  }

  const addNote = ()=> {
    if(newNote.value.trim.length<9){
      return errorMessage.value = "Note should be more than 10 charecters"
    }
    notes.value.push({
      id: Math.floor(Math.random() * 1000000),
      text: newNote.value,
      date: new Date(),
      backgroundColor: getRandomColor()
    });
    showModal.value = false;
    newNote.value =''; 
    errorMessage.value = "";   
  
  }
</script>

<template>
  <main>
    <div v-if="showModal" class="overlay">
      <div class="modal">
        <textarea v-model.trim="newNote" name="note" id="note" cols="30" rows="10"></textarea>
        <p v-if="errorMessage">{{errorMessage}}</p>
        <button  @click="addNote()"> Add Note</button>
        <button @click="showModal = false, newNote ='' " class="close"> Close</button>
      </div>
    </div>
    <div class="container">
      <header>
        <h1>Notes</h1>
        <button @click="showModal = true">+</button>
      </header>
      <div class="cards-container">
        <div v-for="note in notes" :key="note.id" class="card" id={{note.id}} :style="{backgroundColor:note.backgroundColor}">
          <p class="main-text"> {{ note.text }} </p>
          <p class="date">{{ note.date.toISOString().split('T')[0]}} /{{ note.date.toTimeString().split(' ')[0]}} </p>
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
    flex-direction: row;
  }

  h1{
    font-weight: bold;
    margin-bottom: 25px;
    font-size: 50px;
  }

  header button{
    border: none;
    padding: 10px;
    width: 50px;
    height: 50px;
    cursor: pointer;
    background-color: rgba(21,20,20);
    border-radius: 100%;
    color: white;
    font-size: 20px;
  }

  .card{
    width: 250px;
    height: 250px;
    background-color: yellow;
    padding: 10px;
    border-radius: 15px;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    margin-right: 20px;
    margin-bottom: 20px;
  }

  .date{
    font-size: 12.5px;
    font-weight: bold;
  }
  
  .cards-container{
    display:flex;
    flex-wrap: wrap;

  }

  .overlay{
    position: absolute;
    width: 100vw;
    height: 100vh;
    background-color: rgba(0,0,0,0.77);
    z-index: 10;
    display: flex;
    align-items: center;
    justify-content: center;

  }

  .modal{
    width: 50%;
    background-color: white;
    border-radius: 15px;
    padding: 30px;
    position: relative;
    display: flex;
    flex-direction: column;
    max-height: 100vh;
  }

  .modal p {
    color: red;
  }
  textarea{
    position: relative;
    max-width: 100%;
    max-height: 30%;
  }

  .modal button{
    padding: 10px;
    font-size: 20px;
    width: 100%;
    background-color: blue;
    border: none;
    color: white;
    cursor: pointer;
    margin-top: 15px;
  }

  .modal .close{
    background-color: red;
    margin-top: 7px;
  }
  @media only screen and (max-width: 600px){
    .modal{
      width: 70%;
    }
  }
</style>