<script setup>
    const pops = defineProps(['cadastraTarefa', 'tarefaTemp', 'trocarFiltro', 'editaTarefaTemp']);
</script>
<template>
    <form @submit.prevent="pops.cadastraTarefa">
        <div class="row">
            <div class="col">
                <input :value="pops.tarefaTemp" @change="pops.editaTarefaTemp" required
                    type="text" placeholder="Digite aqui a descrição da tarefa" class="form-control">
            </div>
            <div class="col-md-2">
                <button class="btn btn-primary">Cadastrar</button>
            </div>
            <div class="col-md-2">
                <select @change="pops.trocarFiltro" class="form-control">
                    <option value="todas">Todas as Tarefas</option>
                    <option value="pendentes">Pendentes</option>
                    <option value="finalizadas">Finalizadas</option>
                </select>
            </div>
        </div>
    </form>
</template>