<template>
  <h2>Tipo de Cuenta: {{ cuenta }}</h2>
  <h2>Saldo: {{ saldo }}</h2>
  <h2>Cuenta {{ estado ? 'Activa' : 'Inactiva' }}</h2>

  <div v-for="(item, indice) in servicios" :key="indice">
      {{ indice + 1}}  {{ item }}
  </div>


</template>

<script>
export default {
    data() {
        return {
            saldo: 1000,
            cuenta: 'Visa',
            estado: false,
            servicios: ['giro', 'abono', 'transferencia']
        }
    },
}
</script>

<style>

</style>