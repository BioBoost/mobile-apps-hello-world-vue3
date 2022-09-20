<script setup lang="ts">
  import { ref, computed } from 'vue'

  // Reactive state
  const clicked = ref(false);

  // 2nd approach
  function button_click() {
    clicked.value = true;
  }

  const text = computed(() => {
    return clicked.value ? 'Clicked' : 'Please Click Me'
  })

  const color = computed(() => {
    return clicked.value ? 'grey' : 'green';
  })

</script>

<template>
  <div>
    <button @click="clicked=true" :disabled="clicked" :class="[color]">
      {{ clicked?'Clicked':'Please Click Me' }}
    </button>
    <button @click="button_click" :disabled="clicked" :class="[color]">
      {{ text }}
    </button>
  </div>
</template>

<style scoped>
.grey {
  background-color: grey;
}
.green {
  background-color: green;
}
</style>