<template>
  <div id="app">
      <!-- if flag is false you cant go out from login-->
      <LoginProyecto v-if="!flag" @changeFlag="recivedMessage" :users="listUsers"></LoginProyecto>
      <!-- if flag is true you will go to the main page -->
      <MainProyecto v-if="flag" @changeFlagFromMain="recivedMessage"></MainProyecto>
      <RegisterProyecto v-if="!flag" @sendRegister="recivedRegister"></RegisterProyecto>
  </div>
</template>

<script>
import LoginProyecto from './components/LoginProyecto.vue';
import MainProyecto from './components/MainProyecto.vue';
import RegisterProyecto from './components/RegisterProyecto.vue';

export default {
  name: 'App',
  components: {
    LoginProyecto,
    MainProyecto,
    RegisterProyecto
  },
  data(){
    return {
      flag: false,
      listUsers: [],
    }
  },
  methods: {
    recivedMessage(){
      this.flag = true;
    },
    recivedRegister(payload){
      this.listUsers.push(payload)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
