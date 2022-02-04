<template>
    <div id="main">
        <main class="body">
          <div id="nav">
            <router-link to="/">Home</router-link> |
            <router-link to="/about">About</router-link> |
            <router-link to="/book">book</router-link> |
            <router-link to="/cart">cart</router-link> |
            <!-- <router-link to="/books">books</router-link> -->
          </div>
          <router-view/>
        </main>
    </div> 
</template>

<script>
  export default {
    name: 'my-main',
  }
</script>