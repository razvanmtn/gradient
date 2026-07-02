<script setup>
    import { ref, watch } from 'vue';

    const emit = defineEmits(['changeColor']);

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
        <h2>Settings panel</h2>

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
        border: 1px solid var(--color-gray);
        background: var(--color-white);
        border-radius: 1rem;
        padding: 2rem;
        width: 300px;
        min-height: 400px;
        position: fixed;
        top: 5rem;
        left: 1rem;
    }
</style>
