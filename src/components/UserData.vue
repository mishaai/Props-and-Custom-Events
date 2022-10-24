<template>
    <section>
      <header><h1>User Data</h1></header>
      <p>Name</p>
      <input type="text" v-on:change="change_val"  title="Name"/>
      <p>Age</p>
      <input type="number"  v-on:change="change_val" title="Age"/>
      <br>
      <button v-on:click="send_out" >Add User Data</button>
      
    </section>
  </template>
  
  <script>
  export default {
      props:['outdata'],
      data(){
          return {
            name:'',
            age:0
             
          }
      },
      methods:{
        send_out(){
            this.$emit('out',[{name:this.name,age:this.age}]);
            console.log('data was sented',[{name:this.name,age:this.age}])
        },
        change_val(event){

           if(event.path[0].__vnode.props.type === 'text') this.name = event.target.value;
           if(event.path[0].__vnode.props.type === 'number') this.age = event.target.value;
            
            console.log(event)
        }
      }
  }
  </script>
  
  <style scoped>
  body {
  margin: 0;

}
  header {
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    margin: 3rem;
    border-radius: 10px;
    padding: 1rem;
    background-color: #1b995e;
    color: white;
    text-align: center;
  }
  input {
  font: inherit;
  border: 1px solid #ccc;
  }
  input:focus {
  outline: none;
  border-color: #1b995e;
  background-color: #d7fdeb;
}
  p {
  font-size: 1.25rem;
  font-weight: bold;
  background-color: #8ddba4;
  padding: 0.5rem;
  color: #1f1f1f;
  border-radius: 25px;
}
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #1d0446;
  background-color: #394aeb;
  color: white;
  padding: 0.05rem 1rem;
  border-radius: 10px;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
button:hover,
button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
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