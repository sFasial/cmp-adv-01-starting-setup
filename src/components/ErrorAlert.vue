<template>
    <dialog class="error-dialog" ref="dialogRef" :open="isOpen">
        <slot>
            <h2>The Default</h2>
        </slot>
        <button @click="closeDialog">Close</button>
    </dialog>
</template>

<script>
export default {
    props: {
        isOpen: {
            type: Boolean,
            required: true
        }
    },
    methods: {
        closeDialog() {
            this.$emit('close');
        }
    }
};
</script>

<style scoped>
.error-dialog {
    position: fixed;
    top: 20vh;
    left: 50%;
    transform: translateX(-50%);
    width: 50%;
    max-width: 500px;
    background-color: #f8d7da;
    border: 1px solid #f5c6cb;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    padding: 1rem;
    box-sizing: border-box;
    text-align: center;
    z-index: 1000;
}

.error-dialog h2 {
    margin-top: 0;
    color: #721c24;
}

.error-dialog button {
    background-color: #f5c6cb;
    border: none;
    padding: 0.5rem 1rem;
    border-radius: 4px;
    cursor: pointer;
    color: #721c24;
    margin-top: 1rem;
}

.error-dialog button:hover {
    background-color: #f1b0b7;
}
</style>
