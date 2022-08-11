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
                    <th>Delete</th>  
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
                    <td class="icon-holder"><img @click="$emit('user-delete',user.id)" src="../assets/trash.png" alt="Delete"/></td>
                </tr>
            </tbody>
                
        </table>
    </div>
</template>

<script>
    export default{
        name : 'Datatable',

        components: {
    },

    props:{
        usersdata:Array
    },

    

   
}

</script>

<style scoped>

.icon-holder{
    display: flex;
    justify-content: center;
}

table{
    margin:auto;
    border-collapse: collapse;
    width:95%;

}



tbody{
    background: white;
}
i{
    cursor: pointer;
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