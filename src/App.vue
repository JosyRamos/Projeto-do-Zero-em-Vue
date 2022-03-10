<template>
<div id="app" >
  <HelloWorld msg="Sistema de Cadastro"/>
  
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}

</script>

<style>
body{
 background-image:url('./assets/imagem8.jpg');
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 50px;

}
.cao{
  width: 10%;
  height: 10%;
 
}
</style>
