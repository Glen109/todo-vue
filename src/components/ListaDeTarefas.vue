<script setup>
const pops = defineProps(['tarefas', 'numeroTarefasPendentes', 'estados']);
</script>
<template>
    <ul v-if="(pops.estados.filtro !== 'finalizadas' && pops.estados.filtro !== 'todas' && numeroTarefasPendentes.length === 0) == false" class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in pops.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada === true }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
    <h2 class="mt-3 text-center" v-else-if="pops.estados.filtro == 'pendentes' && numeroTarefasPendentes.length === 0" >Não há Tarefas</h2>
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>
