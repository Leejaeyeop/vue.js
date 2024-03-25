<template>
  <div>Options</div>
</template>

<script lang="ts">
export default {
  props: {
    value: String,
    colors: {
      type: Array,
      default: () => {
        console.log(this)
        return ['#f00', '#ccff00', '#eee', '#0f0']
      }
    }
  },
  beforeCreate() {
    console.log(this)
  },
  //   mounted() {
  //     console.log('value', this.$props)
  //   },
  data() {
    return {
      test: 1
    }
  }
}
</script>

<style scoped>
.swatcher_item {
  background: #eee;
  display: inline-block;
  width: 30px;
  height: 30px;
  margin: 4px;
  border-radius: 60px;
  position: relative;
  cursor: pointer;
}
.swatcher_item:hover,
.swatcher_item.active {
  box-shadow: 0 0 2px rgba(0, 0, 0, 0.9);
}
.swatcher_item.active svg {
  position: absolute;
  top: 5px;
  left: 5px;
  width: 20px;
  height: 20px;
}
</style>
