<script setup>
import { ref } from 'vue';


const emit = defineEmits(['error']);

const randomNumber = ref(0);
const minVal = ref(0);
const maxVal = ref(100);


const generateRandomNumber = (min, max) => {
 if (max < min) {
  return;
 }

  randomNumber.value = Math.floor(Math.random() * (max - min + 1)) + min;
};

</script>


<template>
<p>Random Number: {{ randomNumber }}</p>
        <!-- Min Input -->
         <input
          v-model.number="minVal"
          type="number"
          class="input"
          placeholder="Min"
         />
        <!-- Max Input -->
         <input
          v-model.number="maxVal"
          type="number"
          class="input"
          placeholder="Max"
         />

        <button class="btn btn-outline" @click="generateRandomNumber(minVal, maxVal)">
            Generate New Number ({{ minVal }}-{{maxVal}})
        </button>

</template>