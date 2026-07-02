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
        border: 2px solid var(--color-accent);
        background: var(--color-accent);
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

