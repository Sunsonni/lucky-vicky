<script setup>
import { ref } from 'vue';
import RandomNumber from './components/RandomNumber.vue';
import CoinFlip from './components/CoinFlip.vue';


const header = ref('Random Number Generator');
const error = ref('')

const activeTab = ref('number');

</script>

<template>
  <div class="mx-auto mt-4 bg-base-100 w-96 shadow-sm ">
    <figure>
      <div class="flex justify-center">
        <div role="tablist" class="tabs tabs-lift">
          <button 
            role="tab" 
            class="tab"
            @click="activeTab = RandomNumber"
          >
            Random Number
          </button>
          <button 
            role="tab" 
            class="tab"
            @click="activeTab = CoinFlip"
          >
            CoinFlip
          </button>
          <a role="tab" class="tab">Tab 2</a>
          <a role="tab" class="tab">Tab 3</a>
        </div>
      </div>
       <div class="card-body">
        <h1 class="card-title">
          {{ header }}
        </h1>
        <component :is="activeTab"/>
       <div class="card-actions justify-end">
    </div>
      </div>
    </figure>
  </div>
  <p v-if="error" class="text-error">{{ error }}</p>

</template>