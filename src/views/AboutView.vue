<script setup lang="ts">
  import SingleFireButton from '@/components/SingleFireButton.vue'
  import { ref } from 'vue'

  const quotes = ref([
    'Chuck Norris breathes air ... five times a day.',
    'Chuck Norris does not sleep. He waits.',
    'Chuck Norris can speak Braille.'
  ])

  setTimeout(() => {
    quotes.value.push('Chuck Norris can slam revolving doors.')
  }, 10*1000);

</script>

<template>
  <div class="about">
    <h1>This is an about page</h1>
    <SingleFireButton />
    <ul>
      <li v-for="(q,i) in quotes" :key="i">{{ i }} : {{ q }}</li>
    </ul>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
