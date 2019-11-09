<template>

  <div>
    <h2>Messages</h2>
    <div slot="form-display-screen-contact">

      Total of {{ messageList.length}}
      <div class="outer-container">
        <div class="container-user">
          <div class="name" v-for="(name, index) in nameList" :item="name" :key="index" >

            <label>Your Name: {{ name }} </label>

          </div>  </div>
        <div class="container-password">
          <div class="message" v-for="(message, index) in messageList" :item="message" :key="index">
            <label>Message: {{ message }}</label>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  import formHelper from './formHelper.vue';
  import formOne from './formOne.vue';
  export default {
    name: "formDisplayContactUs",
    props:{
      nm: {
        type: String
      },
      msg: {
        type: String
      },
     // isShowing: false
    },
    components:{
      'form-One': formOne,
      'form-helper': formHelper,
    },
    data: function () {
      return {
        nameList: [],
        messageList: []
      };
    },
    watch:{
      nm: function () {
        this.nameList.push(this.nm);

      },
      msg: function () {
        this.messageList.push(this.msg);
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