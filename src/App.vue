<script setup>
  import {ref} from "vue"

  const showModal = ref(false)
</script>

<template>
  <main>
    <div class="overlay">
      <div class="modal">
        <textarea name="note" id="note" cols="30" rows="10"></textarea>
        <button > Add Note</button>
        <button class="close"> Close</button>
      </div>
    </div>
    <div class="container">
      <header>
        <h1>Notes</h1>
        <button @click="showModal = true">+</button>
      </header>
      <div class="cards-container">
        <div class="card">
          <p class="main-text"> Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptate tenetur harum molestiae a, laborum earum iusto, nihil modi, nemo repellendus neque. Omnis, possimus doloremque. Eveniet quod neque cumque earum laboriosam!</p>
          <p class="date">08/09/2022</p>
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