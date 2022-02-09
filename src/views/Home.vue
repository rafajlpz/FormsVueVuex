<template>
  <form @submit.prevent="darAlta">
    {{dameNombreCientifico}}
    <input
      type="text"
      class="form-control my-2"
      placeholder="Ingrese nombre"
      v-model="especie.nombre"
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
      <button>Enviar</button>
    </div>
  </form>
  <table>
    <tr>

    </tr>
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
  props:{

  },
  data() {
    return {
      especies: [],
      especie: {
        genero:"",
        especie: "",
        nombre: "",
        categorias: [],
        tipo: ''
      },
    };
  },
  computed:{ //Dentro solo hay funciones que retornan algo
    dameNombreCientifico(){
      return `${this.especie.especie} ${this.especie.genero}`
    }
  },
  methods:{ //Dentro solo hay funciones, pueden o no retornar algo.
    darAlta(){
      alert()
    }
  }
};
</script>
