<template>
  <div id="app">

    <nav>
      <div class="nav-wrapper blue darken-1">
        <img width="15%" src='/asset/logoVough.png'>
        <a href="#" class="brand-logo center">CLIENTES EM POTENCIAL</a>
      </div>
    </nav>

    <div class="container">

      <!--<form>
          <label>Id</label>
          <input type="text" placeholder="Id">
          <label>Nome</label>
          <input type="text" placeholder="Nome">
          <label>E-mail</label>
          <input type="text" placeholder="Companhia">
          <label>Company</label>
          <input type="text" placeholder="Valor">

          <button class="waves-effect waves-light btn-small">Salvar<i class="material-icons left">save</i></button>

      </form> -->

      <table class="responsive-table">

        <thead>
          <!--onde sera feito o consumo da API-->
          <tr>
            <th>id</th>
            <th>Nome</th>
            <th>E-mail</th>
            <th>Company</th>
            <th>OPÇÕES</th>
          </tr>

        </thead>

        <tbody>

          <tr v-for="user in users" :key="user.id">

            <!--onde está sendo  feito o consumo da API-->
            <td>{{user.id}}</td>
            <td>{{user.name}}</td>
            <td>{{user.email}}</td>
            <td>{{user.company}}</td>
           <!-- <td>
              <button class="waves-effect btn-small blue darken-1"><i class="material-icons">create</i></button>
              <button class="waves-effect btn-small red darken-1"><i class="material-icons">delete_sweep</i></button>
            </td> -->

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

<style>

</style>
