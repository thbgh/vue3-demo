<script setup lang="ts">
import { reactive, ref } from 'vue'
// 组合式API结合Pinia
import { useCounterStore } from '@/stores/counter'
const store = useCounterStore()
// reactive 数据
const state = reactive({ inputValue: 0 })
function submit() {
  console.log({ inputValue: state.inputValue })
  console.log({ count: count.value })
  // state.inputValue++
}
// ref 数据
const count = ref('a')
</script>
<template>
  <div class="about">
    <strong>组合式API(setup)结合Pinia</strong>
    <h1>This is an about page</h1>
    <button @click="store.increment()">Add</button>
    <div>
      {{ store.count }}
    </div>
    <a-button type="primary">Primary Button</a-button>
    <a-date-picker />
    <a-steps :current="1">
      <a-step>
        <!-- <span slot="title">Finished</span> -->
        <template #title>Finished</template>
        <template #description>
          <span>This is a description.</span>
        </template>
      </a-step>
      <a-step title="In Progress" sub-title="Left 00:00:08" description="This is a description." />
      <a-step title="Waiting" description="This is a description." />
    </a-steps>
    <a-input-group compact>
      <a-input v-model:value="count" style="width: calc(100% - 200px)" />
      <a-input v-model:value="state.inputValue" style="width: calc(100% - 200px)" />
      <a-button type="primary" @click="submit()">Submit</a-button>
    </a-input-group>
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
