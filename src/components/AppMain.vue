<script setup>
import {Card, SearchButton, SelectArchetype, Loader} from "./UI/index.js";
</script>

<template>
  <main class="main">
    <div class="search-container d-flex justify-content-center p-3">
      <select-archetype
          class="rounded-2"
          :archetypes="archetypesAll"
          @selected-archetype="handleSelect"
      />
      <h1>{{ }}</h1>
      <search-button class="ms-3" @click="searchCardByArchetype">Search</search-button>
    </div>
    <div class="container cards-container p-4">
      <div class="search-info p-2">
        <h3 class="txt m-0">Found {{ store.archetypes.length }} cards</h3>
      </div>
      <loader v-if="isLoading"/>
      <div v-else-if="store.archetypes.length === 0"><h1>Select archetype and click search button.</h1></div>
      <div v-else class="cards-container__cards">
        <card
            v-for="(card, index) in store.archetypes"
            :key="index"
            :name="card.name"
            :img-src="card.card_images[0].image_url"
            :race="card.race"
        />
      </div>
    </div>

  </main>
</template>

<script>
import axios from "axios";
import {store} from "../store.js";

export default {
  data() {
    return {
      selectArchetypeInput: '',
      store,
      archetypesAll: [],
      isLoading: true,
      fetchLimit: 50, // Number of items to fetch in each request
      fetchOffset: 0, // Starting index of the items
      foundedCards: "null"
    }
  },
  created() {
    this.fetchCardList()
    this.fetchArchetypes()
  },
  methods: {
    handleSelect(option) {
      this.selectArchetypeInput = option;
    },
    async fetchCardList() {
      const requestURL = `https://db.ygoprodeck.com/api/v7/cardinfo.php?num=${this.fetchLimit}&offset=${this.fetchOffset}`;
      try {
        const response = await axios.get(requestURL);
        this.store.cardList = response.data.data;
        setTimeout(() => {
          this.isLoading = false;
        }, 500)
      } catch (error) {
        console.error("Error fetching card list:", error);
      }
    },
    async fetchArchetypes() {
      const requestURL = "https://db.ygoprodeck.com/api/v7/archetypes.php"
      try {
        const response = await axios.get(requestURL);
        this.archetypesAll = response.data;
      } catch (error) {
        console.error("Error fetching archetypes list:", error);
      }
    },
    async searchCardByArchetype() {
      if (this.selectArchetypeInput !== '') {
        this.isLoading = true;
        const requestURL = `https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${this.selectArchetypeInput}`
        try {
          const response = await axios.get(requestURL);
          this.store.archetypes = response.data.data;
          console.log(response.data)
        } catch (error) {
          console.error("Error searching by archetype:", error);
        } finally {
          this.isLoading = false;
        }
      } else {
        console.log("select archetype to search")
      }
    }
  }
}
</script>

<style lang="sass" scoped>
.cards-container
  background-color: white


  .search-info
    background-color: #212529

    .txt
      color: white

.cards-container__cards
  $grid-gap: 20px
  $grid-cols: 5

  display: grid
  grid-template-columns: repeat($grid-cols, 1fr)
  gap: $grid-gap


</style>