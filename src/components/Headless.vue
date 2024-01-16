<script setup lang="ts">
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
