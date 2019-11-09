<template>
  <div class="container">
    <keep-alive>

     <component  @inputName="updateName" @inputMessage="updateMessage" @inputData="updateUser" @inputPass="updatePass" v-bind:is="component"></component>
      <!--<component @inputName="updateName" @inputMessage="updateMessage" v-bind:is="componentOne"></component> -->
      <!--<component @inputData="updateUser" v-bind:is="component"></component>
            <component @inputPass="updatePass" v-bind:is="component"></component> -->
      <!-- <form-two @inputData="updateUser" @inputPass="updatePass"  /> -->


    </keep-alive>

    <button v-on:click="component ='form-one', isHidden= true">Show form one</button>
    <button v-on:click="component ='form-two',   isHidden= false" >Show form two</button>
    <keep-alive>
      <form-display-screen-login v-if="!isHidden" :usr="childData" :pw="childDataPw"/>

      <form-display-screen-contact :nm="childDataName" :msg="childDataMessage"/>
    </keep-alive>
  </div>
</template>

<script>
  import formOne from './components/formOne.vue';
  import formTwo from './components/formTwo.vue';
  import formDisplayLogIn from './components/formDisplayLogIn.vue';
  import formDisplayContactUs from './components/formDisplayContactUs.vue';
  export default {
    name: "App",
    components:{
      'form-one': formOne,
      'form-two': formTwo,
      'form-display-screen-login': formDisplayLogIn,
      'form-display-screen-contact': formDisplayContactUs
    },
    data(){
      return {
        component: 'form-two',
       // componentTwo:'form-Two',
      //componentOne: 'form-one',
        componentContact: 'form-display-screen-contact',
        componentDisplay: 'form-display-screen-login',
        childData: "",
        childDataPw: "",
        childDataName: "",
        childDataMessage: "",
        isHidden: false
      };
    },
    methods:{
      updateUser(variable){
        this.childData= variable;
      },
      updatePass(varPass){
        this.childDataPw= varPass;
      },
      updateName(variableName){
        this.childDataName= variableName;
      },
      updateMessage(varMsg){
        this.childDataMessage= varMsg;
      }
    }
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Noto+Sans+SC&display=swap');
  body{
    font-family: 'Noto Sans SC', sans-serif;

  }
  h1, h2 {
    font-weight: normal;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
  .container{
    width: 300px;
    border: 2px solid lightcoral;
    margin: 0 auto;
    padding: 10px;
    background-color: #fff;
  }
  button {
    border: 1px solid black;
    background-color: transparent;
  }
  button:hover{
    background-color: lightcoral;
  }
</style>