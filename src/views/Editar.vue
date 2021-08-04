<template lang="">
    <div>
        editar {{$route.params.id}} - {{tarea}}
        <form @submit.prevent="updateTarea(tarea)">
            <Input :tarea="tarea" />
        </form>
    </div>
</template>
<script>
import {mapState, mapActions} from 'vuex'
import Input from '../components/Input.vue'
export default {
    components: {
        Input
    },

    created() {
        this.setTarea(this.$route.params.id)
    },
    methods: {
        ...mapActions(['setTarea', 'updateTarea'])
    },
    
    computed: {
        ...mapState(['tarea'])
    }
    
}
</script>
<style lang="">
    
</style>