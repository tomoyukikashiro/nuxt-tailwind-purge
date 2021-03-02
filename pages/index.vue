<template>
  <div class="container">
    <div>
      <Logo />
      <p>リロード毎に、ランダムで↓の色が青と赤に変わります</p>
      <h1 class="title" :class="cls">nuxt-tailwind-purge</h1>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@nuxtjs/composition-api';

function isEven() {
  return Math.floor(Math.random() * Math.floor(10)) % 2 === 0;
}

export default　defineComponent({
  setup() {
    const cls = isEven() ? 'text-blue-800' : 'text-red-800'
    return {
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
  letter-spacing: 1px;
}
</style>
