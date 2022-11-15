<template>
  <main>
    <div class="container">
      <header>
        <h1>Notes</h1>
        <button>+</button>
      </header>
      <div class="cards-container">
        <div class="card">
          <p class="main-text"> Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptate tenetur harum molestiae a, laborum earum iusto, nihil modi, nemo repellendus neque. Omnis, possimus doloremque. Eveniet quod neque cumque earum laboriosam!</p>
          <p class="date"></p>
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

  button{
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
</style>