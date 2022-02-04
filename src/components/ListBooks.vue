<template>
    <section>
        <!-- <h2>Bilbo le Hobbit</h2>
            <div class="book_info">
                <div class="cover">
                    <img :src="book.image" alt="book cover">
                    <div class="menu">
                        <h3 class="menu_synopsis">synopsis</h3>
                        <h3 class="menu_info">Information</h3>
                        <hr>
                    </div>
                </div>
                <div class="info">
                    <p class="price">Prix : {{book.price}}&euro;</p>
                    <p>Auteur : {{book.writer}}</p>
                    <p>Publié le {{book.publication}}</p>
                    <p>Edition : {{book.edidion}}</p>
                    <p>{{book.format}}</p>
                    <p>Nombre de page : {{book.page}}</p>
                </div>
                <p class="synopsis">{{book.summary}}</p>
            </div>
            
            <button class="button_hover">
                <i class="fas fa-cart-plus"></i>
                Ajouter au panier
            </button> -->
    </section>
</template>

<script>

  export default {
    name: 'list-books'
    // data: function choice() {
    //     return {
    //       book: [],
    //     }
    //   },
    // beforeCreate: function(){
    //   fetch("json/cart.json")
    //   .then(response => response.json())
    //   .then(result => {
    //         let book_information = { image:result.book[0].img, title:result.book[0].title, writer:result.book[0].writer, price:result.book[0].price, publication:result.book[0].publication_date, edidion:result.book[0].edition, page:result.book[0].page_number, format:result.book[0].format, summary:result.book[0].summary }
    //         this.book.push(book_information);  
    //   });
    // }
}
</script>