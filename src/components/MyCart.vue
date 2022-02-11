<template>
<div id="cart">
  <table v-if="books.length > 0">
    <caption>Mon panier</caption>
    <thead>
      <tr>
        <th v-for="column in columns" :key="column">
          {{ column }}
        </th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="book in books" :key="book.id" >
        <td>
          <router-link :to="{ name: 'book', params:{bookId: book.id}}">
          <div class="link">
            <a href="#"><img :src="book.image" alt="cover"></a>
          </div>
          </router-link>
        </td>
        <td data-label="Titre">
          <router-link :to="{ name: 'book', params:{bookId: book.id}}">
          <div>{{book.title}}</div>
          </router-link>
        </td>
        <td data-label="Auteur">
          <div>{{book.writer}}</div>
        </td>
        <td data-label="Prix (unitaire)">
          <div>{{book.price}}&euro;</div>
        </td>
        <td data-label="Quantité">
          <div class="more_less">
            <input type="number" class="quantity" name="quantity" min="0" v-model="book.quantity" value="book.quantity">
            <div class="button_more_less">
              <div class="more" v-on:click="changeQuantity(book, 1)">
                <p>+</p>
              </div>
              <div class="less" v-on:click="changeQuantity(book, -1)">
                <p>-</p>
              </div>
            </div>
          </div>
        </td>
        <td data-label="Prix (total)">{{book.quantity * book.price}}&euro;</td>
        <td data-label="Supprimer"><div class="delete" v-on:click="deleteBook(book)"><i class="fas fa-times"></i></div></td>
      </tr>
    </tbody>                
  </table>
  <h3 v-else>Votre panier est vide</h3>

  <!-- TOTAL CART-->
  <total-cart :books="books"></total-cart>
</div>
</template>

<script>
  import TotalCart from './TotalCart.vue'

  export default new Vuex.Store({
      name: 'my-cart',
      components: {
        TotalCart
      },
      state: {
          books: [],
          columns: ['', 'Titre', 'Auteur', 'Prix (unitaire)', 'Quantité', 'Prix (total)', 'Supprimer']
        },
      beforeCreate: function(){
        fetch("json/cart.json")
        .then(response => response.json())
        .then(result => {
            for(let i = 0; i < result.cart.length; i++){
                let book = { id:result.cart[i].id, image:result.cart[i].img, title:result.cart[i].title, writer:result.cart[i].writer, price:result.cart[i].price, quantity:result.cart[i].quantity }
                this.books.push(book);
            }
        });
      },
      methods: {
          deleteBook(book) {
              this.books.splice(this.books.indexOf(book), 1);
          },
          changeQuantity(book, modificator){
            if(modificator > 0 || (modificator < 0 && book.quantity > 1)){
                book.quantity = parseInt(book.quantity) + modificator;
            }
          }
      },
      watch: {
          shippingChoice: function(value){
              console.log(value)
          }
      }
  })
</script>