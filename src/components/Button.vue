<template>
    <button class="btn">{{text}}</button>
</template>

<script>

    export default{
        name : 'Button',

        props:{
            text:String
        }
    }

</script>

<style scoped>
.btn{
    margin:10px;
    width:150px;
    font-size: 20px;
    border:none;
    background: rgb(43, 151, 151);
    color:white;
    border-radius: 10px;
    cursor:pointer;
}

.btn:hover{
    background: rgb(26, 90, 90);
}
</style>