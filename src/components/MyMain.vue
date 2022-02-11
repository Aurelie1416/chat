<template>
    <div id="my_main">
        <main class="body">
          <div id="nav">
            <router-link :to="{name: 'Home'}">Home</router-link> |
            <router-link :to="{name: 'About'}">About</router-link> |
            <router-link :to="{name: 'cart'}">cart</router-link> |
            <router-link :to="{name: 'books'}">books</router-link>
          </div>
          <router-view/>
        </main>
    </div> 
</template>

<script>

  export default new Vuex.Store({
    name: 'my-main',
    state: {
        book: null,
      },
    beforeCreate: function(){
      fetch("json/cart.json")
      .then(response => response.json())
      .then(result => {
          this.book = { bookId:result.books[0].id }
      });
    }
  })
</script>