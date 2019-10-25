<template>
  <div>
    <form-helper>
      <div slot="form-header">
        <h3>Form Two - Login</h3>
        <p> Enter your details</p>
      </div>
      <div slot="form-fields">
        <input type="text" v-model="user" placeholder="username"  />
        <input type="password" v-model="password" @keyup.enter="submitPass" placeholder="password"  />

      </div>
      <div slot="form-controls">
    <button v-on:click="submitUser(); submitPass()">Login</button>
      </div>


    </form-helper>
  </div>
</template>

  <script>
  import formHelper from './formHelper.vue'
  export default {
name: "formTwo",
    components:{
      'form-helper': formHelper
    },
    data(){
      return {
          user: '',
          password: '',
      }
    },
    methods:{
  submitUser: function () {
this.$emit("inputData", this.user);
this.user = "";
  },
      submitPass: function () {
        this.$emit("inputPass", this.password);
        this.password = "";
      }

    }
  }
</script>

<style scoped>

</style>