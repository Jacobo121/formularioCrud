<template>
  <!-- @Submit hace que se prosece el formulario y el prevent es para que no se recargue la pagina cuando se prosece -->
 <form @submit.prevent="procesarFormulario">
   <Input :tarea="tarea" />
 </form>

  <hr>
 <p>
   {{tarea}}
 </p>
</template>

<script>
// @ is an alias to /src
import Input from '../components/Input.vue'

export default {
  name: 'Home',
  components: {
    Input
  },

  data() {
    return {
      tarea: {
        nombre: "",
        categorias: [],
        estado: "",
        numero: 0
      },

    }
  },

  methods: {
    procesarFormulario() {
      console.log(this.tarea)
      if(this.tarea.nombre.trim() === "") {
        console.log('Campo vacio')
        return
      }
      console.log('el campo no esta vacio')
      //enviar datos

      this.tarea = {
        id: '',
        nombre: "",
        categorias: [],
        estado: "",
        numero: 0
      }
    },
  },

  
}
</script>
