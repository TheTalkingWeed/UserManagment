<template>
  <div>
    <Header @show-user-adder="showUserAdder" @delete-users="usersDelete" text="User managment" :showUserAdd="showUserAdd"></Header>
    <div v-if="showUserAdd">
    <UserAdder @user-add="addUser"></UserAdder>
    </div>
    <h2>All users: {{usersnum}}</h2>
    <Datatable  :usersdata="userdata" @user-delete="deleteUser"></Datatable>

    
  </div>
</template>

<script>

import Header from './components/Header.vue'
import Datatable from './components/Datatable.vue'
import UserAdder from './components/UserAdder.vue'


export default {
  name: 'App',
  components: {
    Header,
    Datatable,
    UserAdder,
},

  data(){
    return{
        userdata : [],
        showUserAdd: false
  }
  },
   computed: {
    usersnum(){
        //iteralsz
        if(this.userdata)
          return this.userdata.length
        else
          return 0
    }
  },

  methods:{
      showUserAdder(){
        this.showUserAdd = !this.showUserAdd;
      },

      async deleteUser(id){
        if(confirm('Are you shure?')){
          const res = await fetch(`api/users/${id}`,{
            method : 'DELETE'
          })

          res.status === 200 ? ( 
          this.userdata = this.userdata.filter((user) => user.id !== id)
          ):alert('Error deleting the user')

        }
      },

      usersDelete(){
        console.log('valami')
      },

      async addUser(user){
        const res = await fetch('api/users', {
          method : 'POST',
          headers :{
          'Content-type': 'application/json'
          },
          body:JSON.stringify(user)
        })

        const data = await res.json()

        this.userdata = [...this.users,data]
      },

      async fetchUsers(){
        const res = await fetch("api/users")

        const data = await res.json()

        return data
      }
    },

    async created(){
      this.userdata = await this.fetchUsers()
    }

  

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
