<template>
  
  <div id="app">

      <nav class="nav-extended amber darken-4 ">
            <div class="nav-wrapper">
                  <img width="220px" height="220px" src="./assets/vough.png" alt="">
                  
            </div>
            <div class="nav-content">
              <span class="nav-title">Lista de Clientes em Potêncial</span>
              <a class="btn-floating btn-large halfway-fab waves-effect waves-light teal">
                <i class="material-icons">add</i>
              </a>
            </div>
      </nav>
       
      <div class="container">
        <table class="responsive-table">

          <thead>
            
                  
                  
                <tr >
                  <th>ID</th>
                  <th>NOME</th>
                  <th>E-MAIL</th>
                  <th>COMPANY</th>
                  <th>WEBSITE </th>
                </tr>
              
            
          </thead>

          <tbody>

            <tr v-for="user in users" :key="user.id">

              <!--onde está sendo  feito o consumo da API-->
              <td>{{user.id}}</td>
              <td>{{user.name}}</td>
              <td>{{user.email}}</td>
              <td>{{user.company.bs}}</td>
              <td><a href="#">{{user.website}}</a></td>
              

            </tr>

          </tbody>
        
        </table>

      </div>

  </div>
</template>

<script>

import axios from 'axios';

export default {

   data() {
    return{
      users: []
    }
  },
  name : 'App',
  created: function(){
    axios.get("https://jsonplaceholder.typicode.com/users/").then(res => {
      console.log(res)
      this.users = res.data

    })
  }

}

</script>

<style scoped>

body{
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 14px;
}
.app{
  width: 100%;
  padding: 20px;
  border: 2px solid rgb(201, 184, 163);
  border-radius : 5px;
  background-color: #c5cae9;
  font-family: 'Courier New', Courier, monospace;

}

.container{
    width: 1200px;
    padding-left: 20px;
    padding-right: 15px;
    
    margin: 10;
    font-family: Arial, Helvetica, sans-serif;
    background-color:#ede7f6 deep;
    

}
.nav-extended{
    
    padding-right: 15px;
    border: 1px solid rgb(233, 153, 50);
    margin: 10;
    font-family: Arial, Helvetica, sans-serif;
  
}
.nav-title{
  padding-top: 10px;
  padding-left: 33%;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  color:white;
  text-align: center;

}

.nav-wrapper{
  padding-top: 10px;
  padding-left: 0%;
  font-family: 'Courier New', Courier, monospace;
  color:white;
  text-align: center;

}

</style>

