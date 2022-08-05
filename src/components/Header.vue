<template>
    <div class="wrapper">
        <h2>{{text}}</h2>
        <Button text="Add user"></Button>
        
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
            text:String
        }
    }
</script>


<style scoped>
.wrapper{
    display: flex;
    justify-content: space-between;
    width:500px;
    margin:auto;
}

</style>