<template>
<div id="app" >
  <img alt="Vue logo" src="./assets/imagem.png" class="cao" >
  <HelloWorld msg="Sistema de Cadastros"/>
  
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 50px;

}
.cao{
  width: 15%;
}
</style>
