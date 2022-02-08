<template>
  <form>
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
      <label for="check-1" class="form-check-label"> Especie 1 </label>
    </div>
    <div class="form-check form-check-inlin">
      <input
        type="checkbox"
        id="check-2"
        class="form-check-input"
        v-model="especie.categorias"
        value="Pino"
      />
      <label for="check-2" class="form-check-label"> Especie 2 </label>
    </div>
  </form>
  <hr />
  <p>
    {{ especie }}
  </p>
</template>

<script>
export default {
  name: "Home",
  components: {},
  data() {
    return {
      especie: {
        nombre: "",
        categorias: [],
      },
    };
  },
};
</script>
