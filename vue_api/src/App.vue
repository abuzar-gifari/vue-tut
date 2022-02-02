<template>
  <h1>User's data</h1>
  <ul class="item" v-for="item in list" :key="item.id">
    <li>{{ item.id }}</li>
    <li>{{ item.email }}</li>
    <li>{{ item.first_name }}</li>
    <li><img :src="item.avatar"></li>
  </ul>


<!-- send data to API with post method -->

  <input type="text" name="email" v-model="email"><br>
  <input type="text" name="password" v-model="password">
  <button v-on:click="addUser()">Enter new user</button>


</template>

<script>
import axios from 'axios';
export default {
  name: 'App',
  data(){
    return{
      list:[],
      email:'',
      password:''
    }
  },
  methods:{
    async addUser(){
      let result= await axios.post("http://localhost:8080/user",{
        email:this.email,
        password:this.password
      })
      console.warn(result);
    }
  },
  async mounted(){
      let result = await axios.get("https://reqres.in/api/users?page=1");
      console.warn(result.data.data);
      this.list=result.data.data;
  }
}
</script>

<style>
.item{

}
.item li{
  display: inline-block;
  border: 1px solid;
  width:180px;
  text-align: center;
  padding: 5px;
}

.item img{
  width:50px;
}
</style>
