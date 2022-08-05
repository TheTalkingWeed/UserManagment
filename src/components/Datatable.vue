<template>
    <div class="datatable-container">
        <table>
            <thead>
                <tr>
                    <th>First name</th>
                    <th>Last name</th>
                    <th>Email</th>
                    <th>Phone number</th>
                    <th>Country</th>
                    <th>Born date</th>
                    <th>Job</th>  
                    <th></th>  
                </tr>
            </thead>
            <tbody>               
                <tr v-for="user in usersdata" :key="user.id">
                    <td>{{user.first_name}}</td>
                    <td>{{user.last_name}}</td>
                    <td>{{user.email}}</td>
                    <td>{{user.phone_number}}</td>
                    <td>{{user.country}}</td>
                    <td>{{user.birth_date}}</td>
                    <td>{{user.job}}</td>
                    <td><Button text="Delete"></Button></td>
                </tr>
            </tbody>
                
        </table>
    </div>
</template>

<script>
import Button from './Button.vue'
    export default{
        name : 'Datatable',
        components: {
    Button,
},
        props:{
            usersdata:Array
        }
    }

</script>

<style scoped>

table{
    margin:auto;
    border-collapse: collapse;
    width:90%;

}

tbody{
    background: white;
}

th{
    background-color:black;
    color:white;
    height: 50px;
    padding: 5px;
}

tr{
    text-align: center;
    cursor:context-menu;
}

tr:hover{
    background-color: #ddd;
}

td{
    border:1px solid #ddd;
    padding: 8px;
    text-align: left;
}


</style>