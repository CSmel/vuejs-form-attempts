<template>

  <div>
    <h2>Failed Login Attempts</h2>
    <div slot="form-display-screen">

     Total of {{ userList.length}}
      <div class="outer-container">
      <div class="container-user">
<keep-alive></keep-alive>
      <div class="user" v-for="(user, index) in userList" :item="user" :key="index" >

        <label>User Name: {{ user }} </label>

      </div>  </div>
      <div class="container-password">
      <div class="password" v-for="(password, index) in passList" :item="password" :key="index">
        <label>Pass Word: {{ password }}</label>
      </div>
      </div>
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
      },
      isShowing: false
    },
    components:{
      'form-Two': formTwo,
      'form-helper': formHelper,
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
  .outer-container{
    display: flex;
    flex-direction: row;
    font-size: 12px;
  }
  .container-user,   .container-password{
    display: flex;
    flex-direction: column;
    width: 50%;
  }

  .password, .user{
    border: 2px solid lightcoral;

  }

</style>