<template>
  <!-- ESTE ES EL COMPONENTE HIJO -->
  <li>{{ nombre }} <button @click="clickEliminar(indice)">Eliminar</button></li>
</template>

<script>
export default {
  name: 'ItemLista',
  props: {
    nombre: String,
    indice: Number
  },
  methods: {
      clickEliminar(indice) {
          // Esto emite un evento llamado eliminarTarea hacia el padre que llama a este componente y le pasa
          // como parametro un indice.
          this.$emit('eliminarTarea', indice);
      }
  },
};
</script>

<style scoped>
</style>