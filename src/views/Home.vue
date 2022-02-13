<template>
  <form @submit.prevent="procesarFormulario">
    <input
      type="text"
      class="form-control my-2"
      placeholder="Ingrese nombre"
      v-model.trim="especie.nombre"
    />
    <div class="form-check form-check-inlin">
      <input
        type="checkbox"
        id="check-1"
        class="form-check-input"
        v-model="especie.categorias"
        value="Roble"
      />
      <label for="check-1" class="form-check-label"> Quercus </label>
    </div>
    <div class="form-check form-check-inlin">
      <input
        type="checkbox"
        id="check-2"
        class="form-check-input"
        v-model="especie.categorias"
        value="Pino"
      />
      <label for="check-2" class="form-check-label"> Pinus</label>
    </div>

    <div class="mt-2">
      <div class="form-check form-check-inlin">
        <input
          type="radio"
          id="radio-1"
          class="form-check-label"
          value="quercus"
          v-model="especie.tipo"
        />
        <label for="radio-1" value="">Robur</label>
      </div>

      <div class="form-check form-check-inlin">
        <input
          type="radio"
          id="radio-2"
          class="form-check-label"
          value="pinus"
          v-model="especie.tipo"
        />
        <label for="radio-2">Pinaster</label>
      </div>
    </div>
    <div class="mt-2">
      <input
        type="number"
        class="form-control"
        v-model.number="especie.numero"
      />
    </div>
    <button
      class="btn btn-dark mt-2 btn-block"
      type="submit"
      :disabled="bloquear"
    >
      Enviar
    </button>
  </form>
  <table>
    <tr></tr>
  </table>
  <hr />
  <p>
    {{ especie }}
  </p>
</template>

<script>
export default {
  name: "Home",
  components: {},
  props: {},
  data() {
    return {
      especie: {
        nombre: "",
        categorias: [],
        estado: "",
        numero: 0,
      },
    };
  },
  computed: {
    //Dentro solo hay funciones que retornan algo
    bloquear() {
      return this.especie.nombre.trim() === "" ? true : false;
    },
  },
  methods: {
    //Dentro solo hay funciones, pueden o no retornar algo.
    darAlta() {
      alert();
    },
    procesarFormulario() {
      console.log(this.especie);
      if (this.especie.nombre.trim() === "") {
        console.log("Campo vacio");
        return;
      }
      console.log("No esta vacio");
      // Enviar datos

      this.especie = {
        nombre: "",
        categorias: [],
        estado: "",
        numero: 0,
      };
    },
  },
};
</script>
