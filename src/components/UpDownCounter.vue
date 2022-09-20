<script setup lang="ts">
  // Component logic / state
  import { ref } from 'vue';

  // Reactive state var
  const counter = ref(0);
    // Alternative: const data = reactive({ counter: 0 })

  const showQuote = ref(false);

  // Normal variable
  let author = 'Nico De Witte'

  function increment() {
    counter.value++;
    showQuote.value = counter.value >= 10;
  }

  function decrement() {
    counter.value--;
    showQuote.value = counter.value >= 10;
  }

</script>

<template>
  <p>Our counter is currently at <span>{{ counter }}</span></p>

  <button v-on:click="increment">Counter UP</button>
  <button @click="decrement">Counter DOWN</button>

  <p>This website was build by {{ author }}</p>

  <p v-if="showQuote">Chuck Norris can dribble a bowling ball.</p>
  <p v-show="showQuote">The main export of Chuck Norris is pain.</p>
</template>