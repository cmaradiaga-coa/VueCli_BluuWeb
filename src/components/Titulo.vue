<template>
  <h1>{{ texto }}</h1>
</template>

<script>
export default {
    // se puede usar props = [] tambien
    name: 'Titulo',
    props: {
        texto: String
    }
}
</script>

// el scoped indica que este estilo es unicamente para este componente.
<style scoped>
    h1 {
        color:hotpink;
    }
</style>