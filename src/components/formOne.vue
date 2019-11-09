<template>
  <div>
    <form-helper>
      <div slot="form-header">
        <h3>Form One - Contact Us</h3>
        <p> information about the form</p>
      </div>
      <div slot="form-fields">
        <label>Your Name:</label>
        <input v-model="name" type="text" placeholder="name"/>
        <br><label>Your Message:</label>
        <textarea v-model="message"></textarea>
      </div>
    </form-helper>
    <div slot="form-controls">
      <button v-on:click="heyMessage();">hey</button>
    </div>
  </div>
</template>
<script>
  import formHelper from './formHelper.vue'

  export default {
    name: "formOne",
    components: {
      'form-helper': formHelper
    },
    data() {
      return {
        name: '',
        message: ''
      }

    },
    methods: {
      heyMessage: function () {
        this.$emit("inputName", this.name);
        this.name = "";
        this.$emit("inputMessage", this.message);
        this.message = "";
      }
    },

  }
</script>
<style scoped>
  input, textarea {
    border-color: cadetblue;
    border-style: solid;
    width: 100%;
  }

  button {
    border-style: solid;
  }
</style>