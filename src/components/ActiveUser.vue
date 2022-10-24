<template>
    <section>
      <header><h1>Active User</h1></header>
      <ul>
          <li v-for="(data,i) in db" :key="i">
                <h2>Name:{{ data.name }}</h2>
                <h3>Age:{{ data.age }}</h3>            
          </li>
      </ul>
    </section>
  </template>
  
  <script>
  export default {
      props:['db'],
      data(){
          return {
             
          }
      }
  }
  </script>
  
  <style scoped>
  
  header {
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    margin: 3rem;
    border-radius: 10px;
    padding: 1rem;
    background-color: #1b995e;
    color: white;
    text-align: center;
  }
  
  h2 {
    font-size: 2rem;
    border-bottom: 4px solid #ccc;
    color: #1b995e;
    margin: 0 0 1rem 0;
  }
  h3 {
    font-size: 2rem;
    border-bottom: 4px solid #ccc;
    color: #21088d;
    margin: 0 0 1rem 0;
  }
  div {
    width: 70%;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    border-radius: 15px;
  }
  
  </style>