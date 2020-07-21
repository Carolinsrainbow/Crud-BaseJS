<template>
  <div class="crud">
    <!-- Inicio Tabla de ingreso  -->
    <input type="nombre" placeholder="Ingresa tu nombre" v-model="nombre" />
    <input type="apellido" placeholder="Ingresa tu apellido" v-model="apellido" />
    <input type="rut" placeholder="Ingresa tu rut" v-model="rut" />
    <input type="email" placeholder="Ingresa tu email" v-model="email" />

    <!-- Ingreso del boton -->
    <button type="button" class="btn btn-info" @click="ingreso">Ingresar</button>
    <!-- Fin del boton  -->

    <!-- Inicio tabla respuestas -->
    <table class="table table-dark">
      <thead>
        <tr>
          <th scope="col">Nombre</th>
          <th scope="col">Apellido</th>
          <th scope="col">Rut</th>
          <th scope="col">Email</th>
          <th scope="col">Opción</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(user,index) in users" :key="index">
          <td>{{user.nombre}}</td>
          <td>{{user.apellido}}</td>
          <td>{{user.rut}}</td>
          <td>{{user.email}}</td>
          <td>
            <button type="button" class="btn btn-warning">Editar</button>
            <button type="button" class="btn btn-danger" @click="Eliminar(index)">Eliminar</button>
          </td>
        </tr>
      </tbody>
    </table>
    <!-- Fin de tabla respuestas -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      nombre: "",
      apellido: "",
      rut: "",
      email: "",
      users: [
        {
          nombre: "Lucero",
          apellido: "Herrera Quevedo",
          rut: 147889999,
          email: "lucero@gmail.com"
        },
        {
          nombre: "Carolina",
          apellido: "Herrera Azolas",
          rut: 567878,
          email: "carolina@gmail.com"
        },
        {
          nombre: "Mauro",
          apellido: "Herrera Azolas",
          rut: 6789789,
          email: "mauro@gmail.com"
        },
               {
          nombre: "Angie",
          apellido: "Herrera Quevedo",
          rut: 6789789,
          email: "Angie@gmail.com"
        }
      ]
    };
  },
  methods: {
    ingreso() {
this.users.push({nombre: this.nombre, apellido: this.apellido, rut: this.rut, email: this.email})
    },
    eliminar(index){
      this.users.splice(index,1)
    }
  }
};
</script>

<style>
</style>