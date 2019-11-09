<template>
  <div>
    <form-helper>
      <div slot="form-header">
        <!--<img v-bind:src="attemptsImage"> -->
        <h3>Form Two - Login</h3>
        <p> Enter your details</p>
      </div>
      <div slot="form-fields">
        <div class="tellMe" >{{displayNotice}}</div>
<label>User Name:
        <input type="text" :style="{'border-color': color}" v-model="user" placeholder="username" maxlength="8"/>
</label>
        <label>Password:

          <input type="text" :style="{'border-color': color}" v-model="password" placeholder="password" maxlength="8"/>
        </label>
      </div>
    </form-helper>
    <div slot="form-controls">
      <button v-on:click=" checkUser();">Login</button>
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
        displayNotice: '',
        color: ''
      }
    },
    computed: {},
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
          this.displayNotice = 'Validation Passed';
          this.color = 'blue';

        } else {
          this.$emit("inputData", this.user);
          this.user = "";
          this.$emit("inputPass", this.password);
          this.password = "";
          this.displayNotice = 'Validation Failed';
          this.color = 'red';
        }
      },
    }
  }
</script>
<style>

  .tellMe {
    background-color: lawngreen;
    height: 50px;
    width: 50px
  }
  input, textarea {
    border-color: cadetblue;
    border-style: solid;
    width: 100%;
  }

  button {
    border-style: solid;
  }

</style>