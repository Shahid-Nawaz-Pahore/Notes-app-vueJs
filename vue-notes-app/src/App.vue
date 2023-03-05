<template>
  <main>
    <div class="container">
      <header>
        <h1>Notes</h1>
        <button>+</button>
      </header>
      <div class="cards-container">
        <div class="card">
          <p class="main-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum recusandae sunt quae sed consectetur omnis harum vero modi voluptatum.</p>
          <p class="date">12/12/2020</p>
        </div>
        <div class="card">
          <p class="main-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum recusandae sunt quae sed consectetur omnis harum vero modi voluptatum.</p>
          <p class="date">12/12/2020</p>
        </div>
        <div class="card">
          <p class="main-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum recusandae sunt quae sed consectetur omnis harum vero modi voluptatum.</p>
          <p class="date">12/12/2020</p>
        </div>
        <div class="card">
          <p class="main-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum recusandae sunt quae sed consectetur omnis harum vero modi voluptatum.</p>
          <p class="date">12/12/2020</p>
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
button{
  background: none;
  padding: 10px;
  width: 50px;
  height: 50px;
  cursor: pointer;
  background-color: rgb(21,20,20);
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

</style> 