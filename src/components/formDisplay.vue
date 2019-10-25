<template>

  <div>
    <h2>Login Attempts</h2>
      <div slot="form-display-screen">
<div v-for="(user, index) in userList" :item="user" :key="index">
        <label>User Name: {{ user }} </label>
</div>
        <div v-for="(password, index) in passList" :item="password" :key="index">
         <label>Pass Word: {{ password }}</label>
        </div>
      </div>
  </div>
</template>
<script>
  import formHelper from './formHelper.vue';
  import formTwo from './formTwo.vue';
  export default {
    name: "formDisplay",
    props:{
      usr: {
        type: String
      },
      pw: {
        type: String
      }
    },

    components:{
      'form-Two': formTwo
    },
    data: function () {
      return {
        userList: [],
        passList: []

    };
    },
 watch:{
      usr: function () {
        this.userList.push(this.usr);
      },
   pw: function () {
        this.passList.push(this.pw);

   }
 }
  }
</script>
<style scoped>
  input, textarea{
    border-color: cadetblue;
    border-style:solid;
    width: 100%;
  }
  button{
    border-style:solid;

  }
  h1{
    height: 50px;
    width: 50px;
    border: coral;
  }
  div{
    border: 2px solid lightcoral;
  }
</style>