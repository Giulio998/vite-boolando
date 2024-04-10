<script>
import AppNavBar from "./components/AppNavBar.vue"
import AppCard from "./components/AppCard.vue"
import AppFooter from "./components/AppFooter.vue"
export default {
  components: {
    AppNavBar,
    AppCard,
    AppFooter,
  },
  data() {
    return {
      cardsArray: [
        {
          brand: "Levis",
          info: "RELAXED FIT TEE UNISEX",
          firstImage: 'src/assets/1.webp',
          secondImage: 'src/assets/1b.webp',
          price: 29.99,
          discount: 50,

        },
        {
          brand: "Prada",
          info: "RELAXED FIT TEE UNISEX",
          firstImage: 'src/assets/2.webp',
          secondImage: 'src/assets/2b.webp',
          price: 39.99,
          discount: 25,

        },
        {
          brand: "Puma",
          info: "RELAXED FIT TEE UNISEX",
          firstImage: 'src/assets/3.webp',
          secondImage: 'src/assets/3b.webp',
          price: 19.99,
          discount: 30,

        },
        {
          brand: "Nike",
          info: "RELAXED FIT TEE UNISEX",
          firstImage: 'src/assets/4.webp',
          secondImage: 'src/assets/4b.webp',
          price: 29.99,
          discount: 15,

        },
        {
          brand: "Adidas",
          info: "RELAXED FIT TEE UNISEX",
          firstImage: 'src/assets/5.webp',
          secondImage: 'src/assets/5b.webp',
          price: 29.99,
          discount: 50,

        },
        {
          brand: "Zara",
          info: "RELAXED FIT TEE UNISEX",
          firstImage: 'src/assets/6.webp',
          secondImage: 'src/assets/6b.webp',
          price: 39.99,
          discount: 60,

        }
      ]
    }
  }

}


</script>

<template>
  <AppNavBar />
  <main class="mainPadding">
    <div class="container">
      <div class="row prodotti">
        <template v-for="(card, index) in cardsArray" :key="index">
          <AppCard :brand="card.brand" :firstImage="card.firstImage" :secondImage="card.secondImage" :price="card.price"
            :discount="card.discount" />
        </template>

      </div>
    </div>
  </main>
  <AppFooter />
</template>

<style></style>
