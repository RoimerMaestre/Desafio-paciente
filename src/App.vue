<template>
  <div>
    <FormularioCitas @formulario-enviado="agregarPaciente" />
    <section id="todo-container">
      <div v-if="pacientes.length === 0">
        <p>Aún no hay consultas registradas</p>
      </div>
      <div :key="index" v-for="(paciente, index) in pacientes">
        <TodoComponent
          :index="index"
          :paciente="paciente"
          @eliminarPaciente="eliminarPaciente"
        />
      </div>
    </section>
   
  </div>
</template>

<script>
import FormularioCitas from './components/FormularioCitas.vue'
import TodoComponent from './components/TodoComponent.vue'


export default {
  name: 'App',
  components: {
    FormularioCitas,
    TodoComponent,
  
  },
  data() {
    return {
      pacientes: []
    };
  },
  
  methods: {
    agregarPaciente(nuevoPaciente) {
      this.pacientes.push(nuevoPaciente);
    },
    eliminarPaciente(index) {
      this.pacientes.splice(index, 1);
    },
  }
}
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */


#todo-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 10px;
} 
/* .todo-item {
  flex: 1 0 30%; 
  margin: 10px;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 4px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
} */

/* Clases para los estados de gravedad */
.leve {
  background-color: green;
  color: white;
}

.moderado {
  background-color: yellow;
  color: black;
}

.grave {
  background-color: red;
  color: white;
}
</style>