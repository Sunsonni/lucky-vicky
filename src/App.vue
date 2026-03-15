<script setup>
import { ref, shallowRef } from 'vue';

import RandomNumber from './components/RandomNumber.vue';
import CoinFlip from './components/CoinFlip.vue';
import Magic8Ball from './components/Magic8Ball.vue';
import WheelOfNames from './components/WheelOfNames.vue';

const tabs = [
  { name: "Random Number Generator", component: RandomNumber},
  { name: "Coin Flip", component: CoinFlip},
  { name: "Magic 8 Ball", component: Magic8Ball},
  { name: "Wheel of Names", component: WheelOfNames},
]

const header = ref('Random Number Generator');
const error = ref('')

const activeTab = shallowRef(tabs[0].component);


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
            v-for="tab in tabs"
            :class="{ 'tab-active': activeTab === tab.component }"
            @click="activeTab = tab.component; header = tab.name"
          >
            {{ tab.name }}
          </button>
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