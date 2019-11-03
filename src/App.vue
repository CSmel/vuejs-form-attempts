<template>
  <div class="container">
    <keep-alive>

      <component @inputData="updateUser" @inputPass="updatePass" v-bind:is="component"></component>
      <!--<component @inputData="updateUser" v-bind:is="component"></component>
            <component @inputPass="updatePass" v-bind:is="component"></component> -->
      <!-- <form-two @inputData="updateUser" @inputPass="updatePass"  /> -->


    </keep-alive>

    <button v-on:click="component ='form-one'">Show form one</button>
    <button v-on:click="component ='form-two'">Show form two</button>
    <form-display-screen :usr="childData" :pw="childDataPw"/>

  </div>
</template>

<script>
  import formOne from './components/formOne.vue';
  import formTwo from './components/formTwo.vue';
  import formDisplay from './components/formDisplay.vue';
  export default {
    name: "App",
    components:{
      'form-one': formOne,
      'form-two': formTwo,
      'form-display-screen': formDisplay
    },
    data(){
      return {
        component:'form-two',
        componentDisplay: 'form-display-screen',
        childData: "",
        childDataPw: ""
      };
    },
    methods:{
      updateUser(variable){
        this.childData= variable;
      },
      updatePass(varPass){
        this.childDataPw= varPass;
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