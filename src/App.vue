<template>
  <div id="app">
    <my-cart></my-cart>
  </div>
</template>

<script>
import MyCart from './components/MyCartToOrder.vue'

export default {
  name: 'App',
  components: {
    MyCart
  }
}
</script>