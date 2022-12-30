<template>
  <div>
      <h1>{{ props.message }}</h1>
  </div>
</template>

<script setup>

const props = defineProps({
  message: String,
})

</script>

<style lang="scss" scoped>

</style>