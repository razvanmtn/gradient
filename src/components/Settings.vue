<script setup>
    import { ref, watch } from 'vue';

    const emit = defineEmits(['changeColor', 'close']);

    const type = ref('solid');

    const color1 = ref('#ffffff');
    const color2 = ref('#ffffff');

    watch(type, () => {
        color2.value = '#ffffff';
    });

    watch([type, color1, color2], () => {
        emit('changeColor', {
            type: type.value,
            color1: color1.value,
            color2: color2.value,
        })
    });
</script>

<template>
    <div class="settings">
        <div class="settings-top">
            <h2>Settings panel</h2>
            <button type="button" @click="emit('close')">x</button>
        </div>

        <select name="type" v-model="type">
            <option value="solid">Solid color</option>
            <option value="gradient">Gradient</option>
        </select>
        
        <div v-if="type === 'solid'">
            <label for="color1">
                Color
                <input type="color" v-model="color1" />
            </label>
        </div>

        <div v-if="type === 'gradient'">
            <label for="color1">
                Color 1
                <input type="color" v-model="color1" />
            </label>

            <label for="color2">
                Color 2
                <input type="color" v-model="color2" />
            </label>
        </div>
    </div>
</template>

<style scoped>
    .settings {
        border-right: 1px solid var(--color-gray);
        background: var(--color-white);
        border-radius: 0;
        padding: 1.5rem 1.5rem;
        width: 300px;
        min-height: 100vh;
        position: fixed;
        left: 0;
        top: 0;
        box-shadow: 0.25rem 0.25rem 1rem rgba(0, 0, 0, 0.08);
    }

    .settings-top {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 2rem;
    }

    button {
        background: transparent;
        border: 0;
    }

    button:hover {
        cursor: pointer;
    }
</style>
