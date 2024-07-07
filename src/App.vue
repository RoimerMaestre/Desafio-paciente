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



#todo-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 10px;
} 

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