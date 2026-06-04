<template>
    <div class="mb-6">
        <div class="text-3xl font-bold text-slate-800">Task Tracking</div>
    </div>
    <div>
        <select v-model="newTaskPriority" name="" id="">
            <option value="Low">Low</option>
            <option value="Medium">Medium</option>
            <option value="High">High</option>
        </select>
    </div>
</template>

<script setup>
    import { ref } from 'vue';
    const newTaskText = ref('');
    const newTaskPriority = ref('Low')
</script>

<style lang="scss" scoped>

</style>