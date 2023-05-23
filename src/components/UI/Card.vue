<script setup>

</script>

<template>
  <div class="card d-flex flex-column">
    <img class="card__img img-fluid" :src="imgSrc" alt="">
    <div class="card__name">{{ name }}</div>
    <div class="card__race">{{ race }}</div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    name:{
      type: String,
      default: "name"
    },
    imgSrc: {
      type: String,
      default: "img"
    },
    race:{
      type: String,
      default: "race"
    }
  },
  data() {
    return {}
  }
}

</script>

<style lang="sass" scoped>
@use "src/main.sass" as *
.card
  background-color: $card-color
  display: flex
  flex-direction: column
  justify-content: space-between

.card__name
  text-align: center
  padding: 10px
  font-weight: bold
  color: white

.card__race
  text-align: center
  padding: 10px
  color: black
  font-weight: 500

</style>