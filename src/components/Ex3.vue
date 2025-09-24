<script>
    export default { 

       // add code here
        data(){
            return{
                logintype: "username",
                email: "Email",
                username: "Username",
                email_des : "Enter your email address",
                user_des: "Enter your username"
            }
        }
    }
</script>

<template>
    <h1>Please select your login option</h1>
    <!-- Add/modify code in the following to have a dropdown list 
        which lets the user to select either to login with username or email -->
    <select v-model="logintype">
        <option value="username"selected>Username login</option>
        <option value="email">Email login</option>
    </select>
    
    <div>
        <label v-if="logintype === 'username'">{{ username }}</label>
        <label v-else>{{ email }}</label>
        <input v-if="logintype === 'username'" :placeholder="user_des">
        <input v-else :placeholder="email_des">
    </div>


    <!-- suggested answer: -->
    <!-- <div v-if="logintype==='username'">
        <label>Username</label>
        <input placeholder="Enter your username">
    </div>
    <div v-else="logintype==='email'">
        <label>Email</label>
        <input placeholder="Enter your email">
    </div> -->
</template>

