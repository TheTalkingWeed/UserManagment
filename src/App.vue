<template>
  <div>
    <Header text="User managment"></Header>
    <UserAdder></UserAdder>
    <Datatable :usersdata="userdata"></Datatable>

    
  </div>
</template>

<script>

import Header from './components/Header.vue'
import Datatable from './components/Datatable.vue'
import UserAdder from './components/UserAdder.vue'

import {users} from '../users.js'

export default {
  name: 'App',
  components: {
    Header,
    Datatable,
    UserAdder,
},

  data(){
    return{
        userdata : users
    }

  },

  

}
</script>

<style>
body{
  background: rgb(151, 204, 229);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}
</style>
