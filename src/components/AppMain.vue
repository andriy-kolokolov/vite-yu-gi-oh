<script setup>
import {Card, Button, Select} from "./UI/index.js";
</script>

<template>
  <main class="main">
    <div class="search-container d-flex justify-content-center p-3">
      <select class="rounded-2">
        <option selected>Open this select menu</option>
        <option value="1">One</option>
        <option value="2">Two</option>
        <option value="3">Three</option>
      </select>
      <Button class="ms-3">Search</Button>
    </div>
    <div class="container cards-container p-4">
      <div class="search-info p-2">
        <h3 class="txt m-0">Found 99 cards</h3>
      </div>
      <div class="cards-wrapper">
        <card name="" src="https://images.ygoprodeck.com/images/cards/6983839.jpg"/>
      </div>
    </div>

  </main>
</template>

<script>
export default {
  data() {
    return {

    }
  },
}
</script>

<style lang="sass" scoped>
.cards-container
  background-color: white

.search-info
  background-color: #212529

  .txt
    color: white
.cards-wrapper
  $grid-gap: 20px
  $grid-cols: 5


  display: grid
  grid-template-columns: repeat($grid-cols, 1fr)
  gap: $grid-gap


</style>