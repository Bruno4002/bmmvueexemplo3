<script setup>
import { ref, computed } from 'vue'

const professor = ref({
    nome: 'Russel',
    disciplinas: [
        'Desenvolvimento Web II', 
        'Desenvolvimento de Aplicativos para Dispositivos Móveis',
        'Nada',
    ]
})

const possuiDisciplinas = computed(() => {
    return professor.value.disciplinas.length > 0 ? 'Sim' : 'Não'
})
const contadormais = ref(0)
const contadormais2 = ref(0)
const soma = computed(() =>{
  return contadormais.value + contadormais2.value
})
const par = computed(() =>{
if(soma.value % 2 == 0) return true
else return false

})

</script>

<template>
    <div>
        <h1>Professor</h1>
        <p>Nome: {{ professor.nome }}</p>
        <p>Possui disciplinas: {{ possuiDisciplinas }}</p>
    </div>
    <div>
      <p>Contador: {{ contadormais }}</p>
      <button @click="contadormais++" >+</button>
      <button @click="contadormais--">-</button>
      <hr>
      <p>Contador: {{ contadormais2 }}</p>
      <button @click="contadormais2++" >+</button>
      <button @click="contadormais2--">-</button>
    </div>
    <div v-if="par">
      <p>Soma:{{soma}}</p>
      <img src="Flamengo.png" alt="5px">
    </div>
    <div v-if="par">
    <div v-if="soma > 10 ">É maior que 10</div>
    <div v-else>É menor que 10</div>
    <div v-if="soma % 2 == 0">É par</div>
    <div v-else>É impar</div>
  </div>

</template>

<style scoped>
</style>
