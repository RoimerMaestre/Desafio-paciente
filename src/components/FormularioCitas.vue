<template>
  <div class="contenedor-formulario">
    <form @submit.prevent="emitirDatos" class="formulario">
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
        <label for="gravedad" :class="{ vacio: !paciente.gravedad }"
          >Gravedad:</label
        >
        <select v-model="paciente.gravedad" id="gravedad">
          <option value="" disabled selected>Seleccionar gravedad</option>
          <option value="leve">Leve</option>
          <option value="moderada">Moderada</option>
          <option value="grave">Grave</option>
        </select>
      </div>
      <div>
        <label for="motivo" :class="{ vacio: !paciente.motivo }">Motivo:</label>
        <textarea
          v-model="paciente.motivo"
          id="motivo"
          :class="{ vacio: !paciente.motivo }"
        ></textarea>
      </div>
      <button :disabled="!formularioValido" type="submit" class="submit-button">
        Agregar
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: "FormularioCitas",
  data() {
    return {
      paciente: {
        Nombre: "",
        fecha: "",
        hora: "",
        gravedad: "",
        motivo: "",
      },
    };
  },
  computed: {
    formularioValido() {
      return Object.values(this.paciente).every((value) => value);
    },
  },
  methods: {
    emitirDatos() {
      this.$emit("formulario-enviado", { ...this.paciente });
      // Limpiar el formulario después de enviar los datos
      this.paciente = {
        Nombre: "",
        fecha: "",
        hora: "",
        gravedad: "",
        motivo: "",
      };
    },
  },
};
</script>

<style scoped>
.contenedor-formulario {
  display: flex;
  justify-content: center;
  padding: 20px;
}

.formulario {
  display: flex;
  flex-direction: column;
  gap: 20px;
  padding: 20px;
  border: 1px solid;
  border-radius: 5px;
  background-color: rgb(241, 229, 213);
}

.form-group {
  display: flex;
  flex-direction: column;
}

.form-group-motivo {
  flex-basis: 100%;
}

textarea {
  width: 100%;
  height: 100px;
}

.submit-button {
  align-self: flex-end;
  padding: 10px 20px;
  background-color: burlywood;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.submit-button:hover {
  background-color: #0056b3;
}

.vacio {
  color: red;
}

.grave {
  background-color: red;
  color: white;
}
</style>
