<script setup lang="ts">
import { DatePicker } from 'ant-design-vue'
// 组合式API结合Pinia
import { useCounterStore } from '@/stores/counter'
const store = useCounterStore()
</script>
<template>
  <div class="about">
    <strong>组合式API(setup)结合Pinia</strong>
    <h1>This is an about page</h1>
    <button @click="store.increment()">Add</button>
    <div>
      {{ store.count }}
    </div>
    <DatePicker />
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
}
</style>
