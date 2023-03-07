<template>
  <div>
    <p>Count: {{ count }}</p>
    <button @click="increment">
      Increment
    </button>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import { useStore } from 'pinia'

export default defineComponent({
  setup () {
    const store = useStore()

    const count = store.state.count

    const increment = () => {
      store.commit('increment')
    }

    return { count, increment }
  }
})
</script>
