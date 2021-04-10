<template>
  <!-- ESTE ES EL COMPONENTE PADRE -->
  <div class="hello">
    <h1>{{ msg }}</h1>
    <label>Tarea:</label>
    <input type="text" v-model="inputMensaje" placeholder="Ingresar nueva tarea" />
    <button @click="agregarTarea">Crear</button>
    <br>
    <h1>Lista</h1>
    <!-- v-on:nombreEvento escucha un evento emitido por el componente hijo y se asigna un method para que maneje ese evento -->
    <ul>
      <ItemLista v-for="(nombre, index) in lista" :key="index + 'lista-todo'" :nombre="nombre" :indice="index" v-on:eliminarTarea="eliminarTarea" />
    </ul>
  </div>
</template>

<script>
import ItemLista from './ItemLista.vue';

export default {
  name: 'ListaTodo',
  data() {
    return {
      lista: [],
      inputMensaje: ''
    }
  },
  components: {
    ItemLista
  },
  methods: {
    agregarTarea() {
      if (this.inputMensaje) {
        this.lista.push(this.inputMensaje);
        this.inputMensaje = '';
      }
    },
    eliminarTarea(indice) {
      // eliminarTarea se ejecuta cuando se emite el evento desde el componente hijo.
      this.lista = this.lista.filter((item, index) => indice !== index);
    }
  },
  props: {
    msg: String
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
  margin: 10px 10px;
}
a {
  color: #42b983;
}
input {
  margin: 0 10px;
}
</style>
