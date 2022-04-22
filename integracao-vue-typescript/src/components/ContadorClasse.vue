<template>
  <div>
      <h3>Contador (Classe)</h3>
      {{ valor }}
      <br>
      {{parOuImpar}}
      <br>
      <button @click="setValor(-1)">Dec</button>
      <button @click="setValor(1)">Inc</button>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator'

@Component
export default class ContadorClasse extends Vue {

    //Props passada para o component
    @Prop(Number) private readonly valorInicial?: number// Para valor opcional -> ? Para valor obrigatório -> !

    private valor: number = this.valorInicial || 0 //Caso o valor incial não tenha sido passado

    public setValor(delta: number) {
        this.valor += delta
    }

    //Propriedade computada
    public get parOuImpar(): string{
        return this.valor % 2 === 0? 'Par': 'Impar'
    }

}


</script>

<style>

</style>