<template>
    <section :class="gravedadClass">
      <h1>Paciente</h1>
      <p>{{ paciente.Nombre }}</p>
      <h1>Fecha</h1>
      <p>{{ paciente.fecha }}</p>
      <h1>Hora</h1>
      <p>{{ paciente.hora }}</p>
      <h1>Gravedad</h1>
      <p>{{ paciente.gravedad }}</p>
      <button @click="eliminarPaciente">Eliminar</button>
    </section>
  </template>
  
  <script>
  export default {
    name: "TodoComponent",
    props: {
      paciente: Object,
      index: Number
    },
    computed: {
      gravedadClass() {
        return {
          leve: this.paciente.gravedad === 'leve',
          moderado: this.paciente.gravedad === 'moderada',
          grave: this.paciente.gravedad === 'grave'
        };
      }
    },
    methods: {
      eliminarPaciente() {
        this.$emit('eliminarPaciente', this.index);
      }
    }
  };
  </script>
  
  <style scoped>
  .todo-item {
    flex: 1 0 30%; /* Ajusta el tamaño de las columnas según sea necesario */
    margin: 10px;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  </style>