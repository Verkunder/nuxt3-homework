<template>
  <div>
    <h1>{{message}}</h1>
    <h2>{{data}}</h2>
    <NuxtLink to="/posts/1"> Go to post</NuxtLink>
    <button @click="visibleHandler">Click me</button>
    <Transition>
      <HelloText v-if="isVisible" :message="'Hello text'" />
    </Transition>
  </div>
</template>

<script setup>

const message = ref('Hello, world!')

setTimeout(() => {
  message.value = 'Test'
}, 1000)

const {data} = await useFetch('https://jsonplaceholder.typicode.com/todos/1')

const isVisible = ref(false)

const visibleHandler = () => {
  isVisible.value = !isVisible.value
}

</script>

<style lang="sass" scoped>

.v-enter-active, .v-leave-active
  transition: opacity 0.5s ease


.v-enter-from, .v-leave-to
  opacity: 0

</style>