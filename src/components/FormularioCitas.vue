<template>
    <div>
      <form @submit.prevent="emitirDatos">
        <div>
          <label for="Nombre" :class="{ vacio: !paciente.Nombre }">Nombre:</label>
          <input type="text" v-model="paciente.Nombre" id="Nombre" />
        </div>
        <div>
          <label for="fecha" :class="{ vacio: !paciente.fecha }">Fecha:</label>
          <input type="date" v-model="paciente.fecha" id="fecha" />
        </div>
        <div>
          <label for="hora" :class="{ vacio: !paciente.hora }">Hora:</label>
          <input type="time" v-model="paciente.hora" id="hora" />
        </div>
        <div>
          <label for="gravedad" :class="{ vacio: !paciente.gravedad }">Gravedad:</label>
          <select v-model="paciente.gravedad" id="gravedad">
            <option value="" disabled selected>Seleccionar gravedad</option>
            <option value="leve">Leve</option>
            <option value="moderada">Moderada</option>
            <option value="grave">Grave</option>
          </select>
        </div>
        <div>
          <label for="motivo" :class="{ vacio: !paciente.motivo }">Motivo:</label>
          <textarea v-model="paciente.motivo" id="motivo" :class="{ vacio: !paciente.motivo }"></textarea>
        </div>
        <button type="submit">Agregar</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    name: "FormularioCitas",
    data() {
      return {
        paciente: {
          Nombre: '',
          fecha: '',
          hora: '',
          gravedad: '',
          motivo: ''
        }
      };
    },
    methods: {
      emitirDatos() {
        this.$emit('formulario-enviado', { ...this.paciente });
        // Limpiar el formulario después de enviar los datos
        this.paciente = {
          Nombre: '',
          fecha: '',
          hora: '',
          gravedad: '',
          motivo: ''
        };
      }
    }
  };
  </script>
  
  <style>
  .vacio {
    color: red;
  }
  .grave {
    background-color: red;
    color: white;
  }
  </style>