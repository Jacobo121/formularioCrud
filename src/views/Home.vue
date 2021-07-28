<template>
  <!-- @Submit hace que se prosece el formulario y el prevent es para que no se recargue la pagina cuando se prosece -->
  <form @submit.prevent="procesarFormulario">
    <Input :tarea="tarea" />
  </form>

  <hr />
  <p>
    <ListaTareas />
  </p>
</template>

<script>
// @ is an alias to /src
import Input from "../components/Input.vue";
import { mapActions } from "vuex";
const shortid = require("shortid");
import ListaTareas from '../components/listaTareas.vue'

export default {
  name: "Home",
  components: {
    Input,
    ListaTareas
  },

  data() {
    return {
      tarea: {
        id: "",
        nombre: "",
        categorias: [],
        estado: "",
        numero: 0,
      },
    };
  },

  methods: {
    ...mapActions(["setTareas"]),

    procesarFormulario() {
      console.log(this.tarea);
      if (this.tarea.nombre.trim() === "") {
        console.log("Campo vacio");
        return;
      }
      console.log("el campo no esta vacio");

      //generar id
      this.tarea.id = shortid.generate();
      console.log(this.tarea.id);

      //enviar datos
      this.setTareas(this.tarea);

      //refrescar el formulario
      this.tarea = {
        id: "",
        nombre: "",
        categorias: [],
        estado: "",
        numero: 0,
      };
    },
  },
};
</script>
