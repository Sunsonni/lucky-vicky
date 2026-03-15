<script setup>
import { ref } from 'vue';

const imageUrl = ref('https://media.geeksforgeeks.org/wp-content/uploads/20231016151817/heads.png');
const result = ref("Heads");
const flipping = ref(false);

const tossCoin = () => {
    if (flipping.value) return;

    flipping.value = true;

    const randomVal = Math.random();
    const faceCoin = randomVal < 0.5 ? "Heads" : "Tails";

    setTimeout(() => {
        result.value = faceCoin

        imageUrl.value = faceCoin === "Heads" ? "https://media.geeksforgeeks.org/wp-content/uploads/20231016151817/heads.png" : "https://media.geeksforgeeks.org/wp-content/uploads/20231016151806/tails.png";
        flipping.value = false;
    }, 500)


}
</script>

<template>
    <img class="coin cursor-pointer"  :class="{ flip: flipping }" :src="imageUrl" @click="tossCoin"/>
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