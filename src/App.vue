<script>
import AppNavBar from "./components/AppNavBar.vue"
import AppCard from "./components/AppCard.vue"
import AppFooter from "./components/AppFooter.vue"
import { store } from "./store"
import axios from "axios"


export default {
  components: {
    AppNavBar,
    AppCard,
    AppFooter,
  },
  data() {
    return {
      store
    }
  },
  methods: {
    getProducts(){
      axios.get("http://localhost:3000/products").then((res)=>{
        this.store.productsArray = res.data;
        
      })
    }
  },
  mounted() {
    this.getProducts()
  },
  

}


</script>

<template>
  <AppNavBar />
  <main class="mainPadding">
    <div class="container">
      <div class="row prodotti">
        <template v-for="card in store.productsArray" >
          <AppCard :brand="card.brand" :frontImage="card.frontImage" :backImage="card.backImage" :price="card.price" :name="card.name" :badges="card.badges" :isInFavorites="card.isInFavorites"/>
        </template>

      </div>
    </div>
  </main>
  <AppFooter />
</template>

<style></style>
