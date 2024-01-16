<script setup lang="ts">
import {ref, onUpdated, onMounted} from "vue"

console.log("dd")

onMounted(()=> {
    console.log("child mounted")
})

onUpdated(()=> {
    console.log("child updated")
})

</script>

<template>
  <div class="greetings">
    <h1 class="green">this is a child component</h1>
        <slot></slot>
  </div>
</template>

<style scoped>
</style>
