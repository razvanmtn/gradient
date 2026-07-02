<script setup>
    import Settings from './components/Settings.vue'
    import ToggleButton from './components/ToggleButton.vue'
</script>

<template>
    <div class="page">
        <ToggleButton />
        <Settings />
    </div>
</template>

<style scoped>
    .page {
        padding: 1rem;
    }
</style>
