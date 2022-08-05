<template>
    <form @submit="onSubmit" class="user-adder-container">
        <div class="input-div">
            <label>First name</label>
            <input type="text" name="fname" v-model="fname" placeholder="First name" required/>
        </div>
        <div class="input-div">
            <label>Last name</label>
            <input type="text" name="lname" v-model="lname" placeholder="Last name" required/>
        </div>
        <div class="input-div">
            <label>Email name</label>
            <input type="email" name="email" v-model="email" placeholder="Email" required/>
        </div>
        <div class="input-div">
            <label>Phone number</label>
            <input type="text" name="phone" v-model="phone" placeholder="Phone number" required/>
        </div>
        <div class="input-div">
            <label>Country</label>
            <input type="text" name="country" v-model="country" placeholder="Country" required/>
        </div>
        <div class="input-div">
            <label>Birth date</label>
            <input type="date" name="bdate" v-model="bdate" placeholder="Birth date" required/>
        </div>
        <div class="input-div">
            <label>Job</label>
            <input type="text" name="job" v-model="job" placeholder="Job" required/>
        </div>

        <input type="submit" value="Save user" class="submitbtn" />
    </form>
</template>

<script>
    export default{
        name:'UserAdder',

        data(){
            return{
                fname :'',
                lname :'',
                email :'',
                phone :'',
                country :'',
                bdate :'',
                job :''
            }
        },
        methods:{
            onSubmit(e){
                e.preventDefault()

                const newUser = {
                    id : Math.floor(Math.random()*10000),
                    first_name :this.fname,
                    last_name :this.lname,
                    email :this.email,
                    phone_number :this.phone,
                    country :this.country,
                    birth_date :this.bdate,
                    job :this.job 
                }

                this.$emit('user-add',newUser);

                this.fname=''
                this.lname=''
                this.email=''
                this.phone=''
                this.country=''
                this.bdate=''
                this.job=''
            }
        }
    }
</script>

<style scoped>
.input-div{
    display: block;
    margin: 10px;
    text-align: left;
}

.submitbtn{
    background: green;
    color:white;
    cursor:pointer;
}

.submitbtn:hover{
        background: rgb(28, 139, 28);

}

label{
    font-weight: bolder;
    color:black;

}
input{
    width:100%;
    height: 30px;
    outline: none;
    border: none;
    border-radius: 5px;
    font-size: 20px;
}

form{
    display:block;
    width:250px;
    height: 500px;
    margin:auto;
}
</style>