<template>
  <div class="Usuarios">
    <h1>USUARIOS</h1>
    <table>
      <thead>
        <tr>
          <th>Id</th>
          <th>Nome</th>
          <th>Sobre Nome</th>
          <th>Idade</th>
          <th>UserName</th>
        </tr>
      </thead>
      <tbody>
        fdhdhdf
        <tr v-for="Usuarios in Usuarios" :key="Usuarios.id">
          <td>
            {{ Usuarios.Id }}
          </td>
          <td>
            {{ Usuarios.Nome }}
          </td>
          <td>
            {{ Usuarios.SobreNome }}
          </td>
          <td>
            {{ Usuarios.Idade }}
          </td>
          <td>
            {{ Usuarios.UserName }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
//import axios from "axios";
import api from '@/services/Api.js';

export default {
  //// eslint-disable-next-line vue/multi-word-component-names
  name: "Usuarios-",
  data() {
    return {
      usuarios: []
    }
  },
  mounted(){
    api.get('/usuario').then(Response => {
      console.log(Response.data);
      this.usuarios = Response.data;
    });
  },
  /**data: () => {
    return {
      Usuarios: [],
    };
  },
   methods: {
    async getUsuarios() {
      const req = await fetch("https://localhost:7018/api/usuario");
      const data = await req.json();
      console.log(data);

      this.Id = data.id;
      this.Nome = data.nome;
      this.SobreNome = data.sobreNome;
      this.Idade = data.idade;
      this.UserNAme = data.UserNAme;
      
    },

    lista: (scope) => {
    axios.get(`https://localhost:7018/api/usuario`).then((res) => {
    console.log(res)
      scope.usuarios = res.data;
     });
    },
  },
  mounted() {
    this.getUsuarios(this);
  },
  //created() {
  //this.getUsuarios(this);
};*/
}
</script>
