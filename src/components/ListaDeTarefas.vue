<script setup>
const props = defineProps(['tarefas']);
</script>

<template>
 <ul v-if="tarefas.length" class="list-group mt-4">
  <li class="list-group-item" v-for="tarefas in props.tarefas">
   <input @change="evento => tarefas.finalizada = evento.target.checked" :checked="tarefas.finalizada" :id="tarefas.titulo"
    type="checkbox">
   <label :class="{ done: tarefas.finalizada }" class="ms-3" :for="tarefas.titulo">
    {{ tarefas.titulo }}
   </label>
  </li>
 </ul>
 <p v-else class="mt-4 ms-3"> Não existe tarefas pendentes!
 </p>
 
</template>

<style scoped>
 .done {
  text-decoration: line-through;
 }
</style>
