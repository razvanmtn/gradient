<script setup></script>

<template>
    <button type="button">
        <img src="../assets/svg/cog.svg" alt="Toggle Button" />
    </button>
</template>

<style scoped>
    button {
        padding: 0.25rem;
        border-radius: 50%;
        border: 0;
        background: var(--color-dark-gray);
        display: flex;
        align-items: center;
        justify-content: center;
    }

    button:hover {
        cursor: pointer;
    }

    button img {
        width: 2rem;
    }
</style>

