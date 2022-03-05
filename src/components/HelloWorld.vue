<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <table class="table table-striped">
      <thead>
      <tr>
        <td>#</td>
        <td>Nome</td>
      </tr>
      </thead>
      <tbody>
         <tr v-for="participantes in Participante" v-bind:key="participantes.id">
        <td></td>
        <td></td>
      </tr>

      </tbody>
    </table>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
      titulo:"Projeto Inicial",
      Participante:[
     {id:1, nome:'josi'},
     {id:2, idade:21},
     {id:3, sexo:'feminino'}
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
  color: #5d44af;
}
</style>
