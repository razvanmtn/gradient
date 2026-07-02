<script setup>
    import { ref } from 'vue';
    import Settings from './components/Settings.vue';
    import ToggleButton from './components/ToggleButton.vue';

    const isSettingsVisible = ref(false);
</script>

<template>
    <div class="page">
        <ToggleButton @click="isSettingsVisible = !isSettingsVisible" />

        <Settings v-if="isSettingsVisible" />
    </div>
</template>

<style scoped>
    .page {
        padding: 1rem;
    }
</style>
