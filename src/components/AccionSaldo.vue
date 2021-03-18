<template>
        <!-- Esta forma es valida, pero No permite enviarle parámetros. Para enviar parametros hacer los métodos aqui
        en el componente Hijo.
        <button @click="this.$emit('accion')">{{ texto }} </button> 
        -->
     <!-- En este caso, el evento click del botón llama al método accion aqui en este componente, y es este método el que
          finalemente emite el evento @accion en el componente padre, el cual ejecuta su método asociado.-->
     <button @click="accion" :disabled="desactivar">{{ texto }} </button>

</template>

<script>
export default {
    props:  {
            texto: String,
            desactivar: {
                type: Boolean,
                default: false
                }
        },
    methods: {
        accion() {
            this.$emit('accion')
        }
    }
}
</script>

<style>

</style>