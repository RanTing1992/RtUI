<template>
  <button @click="increment">
    {{ state.count }}
  </button>
</template>

<script setup>
import { reactive ,ref} from 'vue'

const state = reactive({ count: 0 })
const s = reactive(false)
const num = ref(0)
function increment() {
    console.log(state,'这个不用value可以访问吗')
    console.log(num.value,'这个呢')
    console.log(s,'这个呢77')
    state.count++
}
</script>