<template>
  <div>
    <form-helper>

      <div slot="form-header">
        <!--<img v-bind:src="attemptsImage"> -->
        <h3>Form Two - Login</h3>
        <p> Enter your details</p>
      </div>
      <div slot="form-fields">
        <div class="tellMe" >{{good}}</div>
        <input  type="text" v-model="user" placeholder="username" maxlength="8"/>
        <input type="text" v-model="password" placeholder="password" maxlength="8"/>
      </div>
    </form-helper>
    <div slot="form-controls">
      <button v-on:click=" checkUser(); submitUser(); submitPass()">Login</button>
    </div>
  </div>
</template>
<script>
  import formHelper from './formHelper.vue'

  export default {
    name: "formTwo",
    components: {
      'form-helper': formHelper
    },
    data() {
      return {
        user: '',
        password: '',
        good: ''
      }
    },
    computed: {


    },
    methods: {

      //  submitUser: function () {
      //  this.$emit("inputData", this.user);
      // this.user = "";
      //},
      //submitPass: function () {
      //  this.$emit("inputPass", this.password);
      //  this.password = "";
      // }
      checkUser: function () {
        if (this.user === 'mel' && this.password === 'password') {
        this.good = 'Validation Passed';
        } else {
          this.$emit("inputData", this.user);
          this.user = "";
          this.$emit("inputPass", this.password);
            this.password = "";
            this.good = 'Validation Failed'
        }
      },
    }
  }
</script>
<style>
  .goodColor{
    border: 2px solid green
  }
  .badColor{
    border: 2px solid red
  }
.tellMe{
 background-color: lawngreen;
    height: 50px;
    width: 50px
     }
</style>