<template>
  <h1>Simple Form</h1>
  <ul>
    <li v-for="item in error" v-bind:key="item">
      {{item}} is invalid
    </li>
  </ul>
  <form>
    <label>Email</label>
    <input type="text" placeholder="enter email" v-model="form.email">
    <br><br>
    <label>Password</label>
    <input type="password" placeholder="enter password" v-model="form.password">
    <br><br>
    <select v-model="form.country">
      <option>India</option>
      <option>Bangladesh</option>
      <option>France</option>
    </select>
    <br><br>
    <h3>Gender</h3>
    <label>Male</label>
    <input type="radio" name="gender" value="male" v-model="form.gender">
    <br><br>
    <label>Female</label>
    <input type="radio" name="gender" value="female" v-model="form.gender">
    <br><br>
    <h3>Technology</h3>
    <label>Java</label>
    <input type="checkbox" value="java" v-model="form.technology">
    <br><br>
    <label>PHP</label>
    <input type="checkbox" value="php" v-model="form.technology">
    <br><br>
    <label>C++</label>
    <input type="checkbox" value="c++" v-model="form.technology">
    <br><br>
    <button type="button" v-on:click="login()">Login</button>
  </form>

  <User item="hello this is gifari"/>

  <!-- Computed Property -->
  <h2>{{ getResult }}</h2>

  <h3>{{ count }}</h3>
  <button v-on:click="count=count+1">+</button>
  <button v-on:click="count=count-1">-</button>

<!--  <Child name="anil sidhu"/>-->
<!--  <Child name="Abuzar Gifari"/>-->
<!--  <Child name="Sk Md"/>-->
<!--  <Child><h1>Code step by step</h1></Child>-->
<!--  <Child><h2>Code step by step</h2></Child>-->
<!--  <Child><img src="https://i.pinimg.com/222x/02/93/a0/0293a06fea5fd23f18b483bea901de36.jpg"></Child>-->

  <Child>
    <!--  nested template can be possible  -->
    <template v-slot:header>
      <h1>Sk Md</h1>
    </template>
    <template v-slot:main>
      <h1>Abuzar</h1>
    </template>
    <template v-slot:footer>
      <h1>Gifari</h1>
    </template>

  </Child>

  <Child>
    <!--  nested template can be possible  -->
    <template v-slot:header>
      <h1>Shahrukh khan</h1>
    </template>
    <template v-slot:main>
      <h1>fggh</h1>
    </template>
    <template v-slot:footer>
      <h1>gfhfhj</h1>
    </template>

  </Child>

  <Child>
    <!--  nested template can be possible  -->
    <template v-slot:header>
      <h1>fhfjj</h1>
    </template>
    <template v-slot:main>
      <h1>adfsgg</h1>
    </template>
    <template v-slot:footer>
      <h1>vddgfd</h1>
    </template>

  </Child>
<!--  <Child></Child>--> <!-- do not pass any html data -->

  <button @click="tab='Java'">Load Java</button>
  <button @click="tab='Node'">Load Node</button>
  <button @click="tab='PHP'">Load PHP</button>

  <component :is="tab"></component>

<!--  Teleport -->

  <teleport to="#footer">
    <Footer />
  </teleport>

</template>

<script>
import User from './User.vue'
import Child from './Child.vue'

import Java from './java.vue'
import Node from './node.vue'
import PHP from './php.vue'

import Footer from './Footer.vue'

export default {
  name:"Home",
  components:{
    User,
    Child,
    Java,
    Node,
    PHP,
    Footer
  },
  data(){
    return{
      tab:"Java",
      form:{
        email:'',
        password:'',
        country:'',
        gender:'',
        technology:[]
      },
      error:[],
      dollars:10,
      rupeeVal:20,
      discount:30,

      // understanding watch property
      count:0
    }
  },
  watch:{
    count(val,prev){
      if (val>=10 && val>prev){
        alert("stop counting");
      }
    }
  },
  computed:{
    getResult(){
      return (this.dollars+this.rupeeVal-this.discount);
    }
  },
  methods:{
    login(){
      // console.warn(this.form);
      this.error=[];
      for (const item in this.form){
        if (this.form[item]==="" || this.form[item].length===0){
          this.error.push(item);
        }
        if (this.error.length===0){
          alert("Data Has Been Submitted!");
        }
        console.warn(this.error);
      }
    }
  }
}
</script>

<style>

</style>
