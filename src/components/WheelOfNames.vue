<script setup>
    import { ref } from 'vue';

    
    const values = ref('');

    const test = () => {
        const array = new Uint32Array(10);
        values.value = crypto.getRandomValues(array);
    }
    test()

</script>

<template>
    <div>
        <p>{{ values }}</p>
    </div>

</template>