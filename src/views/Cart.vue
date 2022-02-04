<template>
  <div class="cart">
    <my-cart-to-order></my-cart-to-order>
  </div>
</template>
<script>

import MyCartToOrder from '../components/MyCartToOrder.vue'

export default {
  name: 'MyCartToOrder',
  components: {
    MyCartToOrder
  }
}

</script>