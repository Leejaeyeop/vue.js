<script setup lang="ts">
import { ref, onUpdated } from 'vue'
import Child from './Child.vue'
import Headless from './Headless.vue'

defineProps<{
  msg: string
}>()

const name = ref<string>('this is test name')
const isActive = true

onUpdated(() => {
  console.log('parent updated')
})
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h3>
      You’ve successfully created a project with
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>. What's next?
    </h3>
    <h4 :class="{ active: isActive }">{{ name }}</h4>
    <input type="text" v-model="name" />
    <Child>
      <div>this is helloword's slot</div>
    </Child>
    <Headless>
      <!-- named scoped slot -->
      <template #header="headerProps">
        {{ headerProps.text }}
        <button>dd</button>
        <button>dd</button>
      </template>
    </Headless>
    <Headless></Headless>
    <Headless></Headless>
  </div>
</template>

<style scoped>
.active {
  color: red;
}

h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
