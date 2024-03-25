<script setup lang="ts">
defineProps({
  colors: {
    type: Array,
    default: () => {
      console.log(this)
      return ['#f00', '#ccff00', '#eee', '#0f0']
    }
  }
})
const text = 'd'
</script>
<template>
  <div>
    <slot name="header" :text="text"></slot>
    <slot name="main"></slot>
    <slot name="footer"></slot>
    <!-- <slot></slot>
    <slot></slot>
    <slot></slot> -->
  </div>
</template>
