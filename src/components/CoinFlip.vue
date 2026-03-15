<script lang="js">
import { ref } from 'vue';

const isHeads = ref(true);
</script>

<template>
<!-- <img v-if="!isHeads" class="coin" src="/public//heads.png" alt="Heads"/> -->

<!-- <img v-else="isHeads" class="coin" src="/public/tails.png" alt="Tails"/> -->

</template>

<style>
body{
    background-color: #fff7fa;
}
.coin{
    display: block;
    width: 20rem;
    margin: auto;
}
</style>