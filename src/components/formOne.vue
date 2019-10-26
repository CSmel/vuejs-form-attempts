<template>
  <div>
    <form-helper>
      <div slot="form-header">
        <h3>Form One - Contact Us</h3>
        <p> information about the form</p>
      </div>
      <div slot="form-fields">
        <label>Your Name:</label>
        <input type="text" placeholder="name" required />
        <br><label>Your Message:</label>
        <textarea></textarea>
      </div>
      <div slot="form-controls">
        <button v-on:click="handleSubmit">Submit</button>
      </div>
    </form-helper>
  </div>
</template>
<script>
  import formHelper from './formHelper.vue'
  export default {
    components:{
      'form-helper': formHelper
    },
    data(){
      return {
      }
    },
    methods:{
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
</style>