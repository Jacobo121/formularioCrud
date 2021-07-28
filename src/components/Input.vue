<template lang="">
  <input
    type="text"
    class="form-control my-2"
    placeholder="Ingrese nombre"
    v-model.trim="tarea.nombre"
  />

  <div class="form-check form-check-inline">
    <input
      class="form-check-input"
      v-model="tarea.categorias"
      type="checkbox"
      id="inlineCheckbox1"
      value="javascript"
    />
    <label class="form-check-label" for="inlineCheckbox1">Javascript</label>
  </div>
  <div class="form-check form-check-inline">
    <input
      class="form-check-input"
      v-model="tarea.categorias"
      type="checkbox"
      id="inlineCheckbox2"
      value="nodeJs"
    />
    <label class="form-check-label" for="inlineCheckbox2">Node.js</label>
  </div>
  <div class="mt-2">
    <div class="form-check form-check-inline">
      <input
        type="radio"
        id="radio-1"
        class="form-check-input"
        v-model="tarea.estado"
        value="urgente"
      />
      <label for="radio-1" class="form-check-label">Urgente</label>
    </div>
    <div class="form-check form-check-inline">
      <input
        type="radio"
        id="radio-2"
        class="form-check-input"
        v-model="tarea.estado"
        value="relax"
      />
      <label for="radio-2" class="form-check-label">Relax</label>
    </div>
  </div>

  <div class="mt-2">
    <input type="number" class="form-control" v-model.number="tarea.numero" />
  </div>

  <button class="btn btn-dark mt-2 btn-block" :disabled="disabledBoton">
    Procesar
  </button>
</template>

<script>

export default {
    props: {
        tarea: Object
    },

    computed: {
        disabledBoton() {
            return this.tarea.nombre.trim() === "" ? true : false
        }
    },
};
</script>

<style lang=""></style>
