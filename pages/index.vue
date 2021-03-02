<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">nuxt-tailwind-purge</h1>
      <div class="links">
        <button type="button" class="border border-red-600 p-8" @click="onClick" :class="cls">Click Me</button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, computed } from '@nuxtjs/composition-api';

export default　defineComponent({
  setup() {
    const flg = ref(false)
    const onClick = () => flg.value = !flg.value
    const cls = computed(() => flg.value ? 'bg-blue-600' : 'bg-yellow-600')
    return {
      onClick,
      cls
    }
  }
})
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
