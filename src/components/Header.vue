<template>
    <div class="wrapper">
        <h2>{{text}}</h2>
        <Button @btn-click="$emit('show-user-adder')" :text="showUserAdd ? 'Close' : 'Add user'" :color="showUserAdd ? 'red' : 'green' "></Button>
        
         
    </div>
</template>

<script>
import Button from './Button.vue'


    export default{
        name : 'Header',

        components: {
            Button,
        },

        props:{
            text:String,
            showUserAdd:Boolean
        },

       
    }
</script>


<style scoped>
.wrapper{
    display: flex;
    justify-content: space-between;
    width:800px;
    height: 70px;
    margin:auto;
}

</style>