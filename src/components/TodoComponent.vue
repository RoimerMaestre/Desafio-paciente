<template>
    <section class="todo-item" :class="gravedadClass">
      <h1>Paciente</h1>
      <p>{{ paciente.Nombre }}</p>
      <h2>Fecha</h2>
      <p>{{ paciente.fecha }}</p>
      <h2>Hora</h2>
      <p>{{ paciente.hora }}</p>
      <h2>Gravedad</h2>
      <p>{{ paciente.gravedad }}</p>
      <h2>Motivo</h2>
      <p>{{ paciente.motivo }}</p>
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
    text-align: center;
    margin: 10px;
    padding: 20px;
    border: 1px solid #727171;
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  </style>