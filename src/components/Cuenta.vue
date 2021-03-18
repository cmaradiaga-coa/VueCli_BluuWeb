<template>
  <h2>Tipo de Cuenta: {{ cuenta }}</h2>
  <h2>Saldo: {{ saldo }}</h2>
  <h2>Cuenta {{ estado ? 'Activa' : 'Inactiva' }}</h2>

  <div v-for="(item, indice) in servicios" :key="indice">
      {{ indice + 1}}  {{ item }}
  </div>
    <br>
    <!-- @accion se captura en el componente Hijo en este caso AccionSaldo -->
    <accion-saldo texto="Aumentar Saldo" @accion="aumentar" />
    <AccionSaldo texto="Disminuir Saldo" @accion="disminuir" :desactivar="desactivar"/>

</template>

<script>
import AccionSaldo from './AccionSaldo.vue'

export default {
  components: { 
          AccionSaldo 
      },
    data() {
        return {
            saldo: 1000,
            cuenta: 'Visa',
            estado: false,
            servicios: ['giro', 'abono', 'transferencia'],
            desactivar:false
        }
    },
    methods: {
        aumentar() {
            this.saldo+= 100;
            this.desactivar = false
        },
        disminuir() {
            if(this.saldo === 0) {
                this.desactivar = true
                alert('Sin Saldo Disponible')
                return
            }
                
            this.saldo-= 100;
        }
    }
}
</script>

<style>

</style>