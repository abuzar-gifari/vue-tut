<template>
<h1> {{ profile }}'s Profile route</h1>
</template>

<script>
import {useRoute} from 'vue-router'
export default {
  name:"Profile",
  data(){
    return{
      profile:''
    }
  },
  mounted() {
    const route=useRoute();
    console.warn("route",route.params.name);
    this.profile=route.params.name;
  }
}
</script>

<style>

</style>
