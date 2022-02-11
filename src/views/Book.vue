<template>
    <my-book></my-book>
</template>
<script>

import MyBook from '../components/MyBook.vue'

export default new Vuex.Store({
    name: 'my-section',
    components: {
      MyBook
    },
    getters: {
      bookId() {
        return this.$route.params.bookId
      }
    },
    methods: {
      goBack() {
        window.history.length > 1 ? this.$router.go(-1) : this.$router.push('/')
      }
    }
  })

</script>