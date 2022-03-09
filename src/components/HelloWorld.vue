<template>
  <div class="container-fluid">
 
    <h1>{{ msg }}</h1>
    <div
      class="alert alert-warning"
      role="alert"
      v-show="participante.length === 0"
    >
      Não existem registros de usuários!
    </div>
    <p>
      Nome:
      <input
        placeholder="Digite seu nome"
        type="text"
        v-model="nome"
        name="nomeParticipante"
        class="form-control"
      />
    </p>
    <p>
      Idade:
      <input
        placeholder="Digite sua idade"
        type="number"
        v-model="idade"
        name="idadeParticipante"
        class="form-control"
      />
    </p>
    <p>
      Sexo:
      <input
        placeholder="Digite seu sexo"
        type="text"
        v-model="sexo"
        name="sexoParticipante"
        class="form-control"
      />
    </p>
    <button class="btn btn-success"  v-on:click="adicionar(index)">
      Adicionar Cadastro
    </button>
    <button class="btn btn-warning" v-on:click="salvar(index)">Salvar</button>
    <table class="table table-striped" v-show="participante.length > 0">
      <thead>
        <tr>
          <td>Código</td>
          <td>Nome</td>
          <td>Idade</td>
          <td>Sexo</td>
          <td>Opções</td>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="(participantes, index) in participante"
          v-bind:key="participantes.id"
        >
          <td>{{ participantes.id }}</td>
          <td>{{ participantes.nome }}</td>
          <td>{{ participantes.idade }}</td>
          <td>{{ participantes.sexo }}</td>
          <td>
            <button class="btn btn-danger" v-on:click="deletar(index)">
              Remover
            </button>
            <button class="btn btn-secondary"  v-on:click="editar(index)">
              Editar
            </button>
          </td>
        </tr>
      </tbody>
    </table>
    
  </div>
</template>
<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      titulo: "Projeto Inicial",
      participante: [],
      id: "",
      nome: "",
      idade: "",
      sexo: "",
      botao: "",
      indice: "",
    
    };
  },
  methods: {
    deletar(index) {
      this.participante.splice(index, 1);
    },
    editandoInfo(index) {
      (this.id = this.participante[index].id),
        (this.nome = this.participante[index].nome),
        (this.idade = this.participante[index].idade),
        (this.sexo = this.participante[index].sexo);
    },
    editar(index) {
      (this.botao = "editar"), (this.indice = index), this.editandoInfo(index);
  
    },
    salvar() {
      
      if (this.botao != "editar") {
        return this.adcionar();
      }
      this.salvandoInfo();
      this.renderizar();
    },
    salvandoInfo() {
      (this.participante[this.indice].id = this.id),
        (this.participante[this.indice].nome = this.nome),
        (this.participante[this.indice].idade = this.idade),
        (this.participante[this.indice].sexo = this.sexo);
    },
    adicionar(index) {
      
      this.participante.push({
        id:Math.random() ,
        nome: this.nome,
        idade: this.idade,
        sexo: this.sexo,
      }
      );
      (this.botao = "adicionar"), this.renderizar(index);
    
    },
    renderizar() {
      (this.id = ""), (this.nome = ""), (this.idade = ""), (this.sexo = "");
    },
  },
};
</script>
<!-- Adicione o atributo "scoped" para limitar o CSS apenas a este componente -->
<style scoped>

</style>


