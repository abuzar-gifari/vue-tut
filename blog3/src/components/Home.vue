<template>
  <h1>Home Page</h1>
</template>

<script>
export default {
  name:"Home",
  components:{

  },
  data(){
    return{
      name:"Gifari",
      counter:0
    }
  },
  methods:{

  },
  // beforeCreate() {
  //   alert("beforeCreate method is called!!");
  // },
  // created() {
  //   alert("created method is called!!");
  // },
  // beforeMount() {
  //   console.warn("beforeMount",this.$el);
  // },
  // mounted() {
  //   console.warn("Mounted",this.$el);
  // },
  beforeUpdate() {
    console.log("beforeUpdate",this.$refs['count'].textContent);
  },
  updated() {
    console.log("updated",this.$refs['count'].textContent);
  }

}
</script>

<style>

</style>