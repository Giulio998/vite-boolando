<script>
import AppNavBar from "./components/AppNavBar.vue"
import AppCard from "./components/AppCard.vue"
import AppFooter from "./components/AppFooter.vue"
import dbJson from "./db.json"

export default {
  components: {
    AppNavBar,
    AppCard,
    AppFooter,
  },
  data() {
    return {
      dbJson
    }
  },
  

}


</script>

<template>
  <AppNavBar />
  <main class="mainPadding">
    <div class="container">
      <div class="row prodotti">
        <template v-for="card in dbJson.products" >
          <AppCard :brand="card.brand" :frontImage="card.frontImage" :backImage="card.backImage" :price="card.price" :name="card.name" :badges="card.badges" :isInFavorites="card.isInFavorites"/>
        </template>

      </div>
    </div>
  </main>
  <AppFooter />
</template>

<style></style>
