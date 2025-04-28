<template>
    <div class="task-card rounded overflow-hidden shadow-lg bg-white w-full">
        <div class="px-6 py-4">
            <strong class="font-bolder text-2xl mb-2">{{ task.title || 'Título Indisponível' }}</strong>
            <p class="text-gray-700 text-base">
                {{ task.description }}
            </p>
            <p class="text-gray-700 text-base">
                Agendada para: {{ formatDate(task.scheduled_to) }}
            </p>

            <p :class="task.is_notified ? 'text-green-500' : 'text-orange-500'">
                {{ task.is_notified ? 'Notificada' : 'Não Notificada' }}
            </p>
        </div>
    </div>
</template>

<script setup>
    import { format } from 'date-fns';
    import { ptBR } from 'date-fns/locale';

    const props = defineProps({
        task: {
            type: Object,
            required: true,
            default: () => ({
                title: '',
                description: '',
                scheduled_to: '',
                is_notified: 0
            })
        }
    });


    const formatDate = (date) => {
        if (!date) return '';
        return format(new Date(date), "dd/MM/yy HH:mm:ss", { locale: ptBR });
    };
</script>

<style scoped>
    .task-card {
        transition: transform 0.2s;
        width: 100%;
        max-width: 800px;
    }

    .task-card:hover {
        transform: scale(1.02);
    }
</style>
