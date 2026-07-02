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
    <div class="page" :style="{ background: gradient }">
        <ToggleButton @click="isSettingsVisible = !isSettingsVisible" />

        <Settings v-show="isSettingsVisible" @changeColor="onColorChange" />
    </div>
</template>

<style scoped>
    .page {
        padding: 1rem;
        width: 100vw;
        height: 100vh;
    }
</style>
