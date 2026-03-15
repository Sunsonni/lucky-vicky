<script setup>
import { ref, shallowRef } from 'vue';

import RandomNumber from './components/RandomNumber.vue';
import CoinFlip from './components/CoinFlip.vue';
import Magic8Ball from './Magic8Ball.vue';


const header = ref('Random Number Generator');
const error = ref('')

const activeTab = shallowRef('RandomNumber');

</script>

<template>
  <div class="mx-auto mt-4 bg-base-100 w-96 shadow-sm ">
    <figure>
      <div class="flex justify-center">
        <div role="tablist" class="tabs tabs-lift">
          <!-- TODO: Switch the way the header changes to a function -->
          <button 
            role="tab" 
            class="tab"
            @click="activeTab = RandomNumber; header = 'Random Number Generator'"
          >
            Random Number
          </button>
          <button 
            role="tab" 
            class="tab"
            @click="activeTab = CoinFlip; header = 'Coin Flip'"
          >
            CoinFlip
          </button>
          <button 
            role="tab" 
            class="tab"
            @click="activeTab = Magic8Ball; header = 'Magic 8 Ball'"
          >
            Magic 8 Ball
          </button>
          <a role="tab" class="tab">Tab 4</a>
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