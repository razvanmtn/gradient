<script setup>
    import { ref } from 'vue';
    import Settings from './components/Settings.vue';
    import ToggleButton from './components/ToggleButton.vue';

    const isSettingsVisible = ref(false);

    const gradient = ref('#ffffff');

    function onColorChange({ type, color1, color2 }) {
        if (type === 'solid') {
            gradient.value = color1;
        } else if (type === 'gradient') {
            gradient.value = `linear-gradient(90deg, ${color1} 0%, ${color2} 100%)`;
        }
    }
</script>

<template>
    <ToggleButton @click="isSettingsVisible = !isSettingsVisible" />

    <div class="page" :style="{ background: gradient }">
        <Settings v-show="isSettingsVisible" @changeColor="onColorChange" @close="isSettingsVisible = false" />
    </div>
</template>

<style scoped>
    .page {
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 1rem;
        width: 100vw;
        height: 100vh;
    }
</style>
