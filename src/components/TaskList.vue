<template>
    <div class="task-list p-6 bg-gray-100 rounded-lg shadow-md w-full">
        <h1 class="text-3xl font-bold text-gray-800 mb-4">Tarefas</h1>
        <ul class="space-y-4 w-full">
            <li v-if="tasks.length === 0" class="text-gray-500">
                Nenhuma tarefa disponível.
            </li>
            <li v-else v-for="task in tasks" :key="task.id" class="p-2">
                <TaskCard :task="task" />
            </li>
        </ul>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import TaskCard from './TaskCard.vue';

const tasks = ref([]);

const fetchTasks = async () => {
    try {
        const response = await fetch(import.meta.env.VITE_API_URL + '/tasks');
        if (!response.ok) {
            throw new Error('Failed to fetch tasks');
        }

        tasks.value = await response.json();
    } catch (error) {
        console.error(error);
    }
};

onMounted(() => {
    fetchTasks();
});
</script>

<style scoped>
    .task-list {
        max-width: 800px;
        margin: 0 auto;
    }
</style>
