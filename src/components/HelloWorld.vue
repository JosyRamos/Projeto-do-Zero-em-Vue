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
    <table class="table table-striped" v-show="participante.length > 0">
      <thead>
        <tr>
          <td>Número</td>
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
            <button class="btn btn-secondary" v-on:click="editar(index)">
              Editar
            </button>
          </td>
        </tr>
      </tbody>
    </table>
    <div class ="modal fade" id="myModal">
      <div class="modal-dialog">
        <div class = "modal-content">
          <div class = "modal-header">
           <button class="btn btn-secondary" v-on:click="editar(index)">
              Editar
            </button>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <form clss="forme-horizontal" method="POST">
            <div class="modal-body"></div>
            <div class="modal-footer">
              <button type="button" class="btn btn-default" data-dismiss="modal">Fechar</button>
              <button type="button" class="btn btn primary">Salvar</button>
            </div>
          </form>
        </div>

      </div>

    </div>
    <div class="form-group">
      <p>
        Código:
        <input
          placeholder="Digite um codigo"
          type="number"
          v-model="id"
          name="idParticipante"
          class="form-control"
        />
      </p>
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
          type="text"
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
      <button class="btn btn-success" v-on:click="adicionar()">
        Adicionar Cadastro
      </button>
      <button class="btn btn-warning" v-on:click="salvar()">Salvar</button>
    </div>
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
    };
  },
  methods: {
    deletar(id) {
      this.participante.splice(id, 1);
    },
    editar() {
    
    },
    adicionar() {
      this.participante.push({
        id: this.id,
        nome: this.nome,
        idade: this.idade,
        sexo: this.sexo,
      });
      (this.id = ""),
       (this.nome = ""), 
       (this.idade = ""), 
       (this.sexo = "");
    },
    salvar() {
      this.participante({});
    },
  },
};
</script>
<!-- Adicione o atributo "scoped" para limitar o CSS apenas a este componente -->
<style>
</style>
