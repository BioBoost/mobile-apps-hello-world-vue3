<script setup lang="ts">
  // Component logic / state
  import { ref, computed } from 'vue';

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

  // Computed methods
  const showChuck = computed(() => {
    return counter.value >= 10
  })

  const color = computed(() => {
    return (counter.value < 10 ? 'red' : 'green')
  })

// style="{color: red}"
</script>

<template>
  <p>Our counter is currently at <span>{{ counter }}</span></p>

  <button v-on:click="increment">Counter UP</button>
  <button @click="decrement">Counter DOWN</button>

  <p v-bind:style="{'color': color}">This website was build by {{ author }}</p>
  <p :style="{'color': color}">This website was build by {{ author }}</p>

  <p :class="color">This website was build by {{ author }}</p>

  <p v-if="showQuote">Chuck Norris can dribble a bowling ball.</p>
  <p v-show="showQuote">The main export of Chuck Norris is pain.</p>
  <p v-if="showChuck">Chuck Norris counted to infinity... twice.</p>
  <img v-if="showChuck" src="https://upload.wikimedia.org/wikipedia/commons/5/5c/Chuck_Norris.jpg" />

  <input type="text" v-model="counter" />
</template>

<style scoped>
.red {
  color: red;
  font-weight: bolder;
}

.green {
  color: green;
  font-weight: bold;
}

</style>