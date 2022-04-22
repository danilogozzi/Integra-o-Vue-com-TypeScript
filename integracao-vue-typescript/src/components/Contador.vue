<template>
  <div>
      <h3>Contador</h3>
      {{valor}}
      <br>
      <button @click="setValor(-1)">Dec</button>
      <button @click="setValor(1)">Inc</button>
  </div>
</template>

<script lang="ts">

import Vue from 'vue'

export default Vue.extend({

    props: {
        valorInicial: {
            type: Number
        },
    },
    data() {
        return{
            valor: this.valorInicial
        }
    },
    methods: {
        setValor(delta: number) {
            this.valor += delta
        },
    },
})
</script>
<style>

</style>