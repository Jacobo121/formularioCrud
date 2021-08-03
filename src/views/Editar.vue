<template lang="">
    <div>
        editar {{$route.params.id}} - {{tarea}}
    </div>
</template>
<script>
import {mapState, mapActions} from 'vuex'
export default {
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