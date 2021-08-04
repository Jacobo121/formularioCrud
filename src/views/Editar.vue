<template lang="">
    <div>
        editar {{$route.params.id}} - {{tarea}}
        <form>
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
        ...mapActions(['setTarea'])
    },
    
    computed: {
        ...mapState(['tarea'])
    }
    
}
</script>
<style lang="">
    
</style>