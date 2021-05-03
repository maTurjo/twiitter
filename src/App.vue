<template>

<div id="app">

  {{fullName}} @ {{user.username}}
  <br>
  {{followers}}
  <br>
  <button  @click="followUser();check()" name="Follow">Follow</button>
  <br><br>
  <span style="border:3px solid red">{{msg}}</span>
</div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      followers:0,
      user:{
        id:1,
        username:'_Turjo',
        firstName:'Mubassir Ahmed',
        lastName:'Turjo',
        email:'ma.turjo@gmail.com',
        isAdmin: true
      },
      msg:""
    }
  },
  watch:{
    followers(n,o){
      o;
      if(n%2==0){
        this.msg="You Just Got A New FOLLOWER ! ! (even)";
      }
      else this.msg="You Just Got A New FOLLOWER ! ! (Odd)";
    }

  },
  computed: {
    fullName(){
      return `${this.user.firstName} ${this.user.lastName}`
    }


  },
  methods:{
    followUser(){
      this.followers++;
    },
    check(){
      if(this.followers>=10){this.followers=0;}
    }


  },

  mounted(){
  //  this.followUser();
   // this.followUser();
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-size: xx-large;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
