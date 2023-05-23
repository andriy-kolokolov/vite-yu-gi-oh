<script setup>

</script>

<template>

  <div class="card d-flex flex-column">
    <div class="card__top d-flex flex-column">
      <div class="card-head d-flex justify-content-between">
        <div class="card-head__name">{{ name }}</div>
        <div class="card-head__attribute">{{ attribute }}</div>
      </div>
      <div class="card__type">{{ type }}</div>
      <img class="card__img img-fluid" :src="imgSrc" alt="">
      <div class="card__description">{{ description }}</div>
    </div>
    <div class="card__bot">
      <div class="card__type">{{ name }}</div>
      <div class="card__type">{{ race }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    name:{
      type: String
    },
    attribute:{
      type: String
    },
    type:{
      type: String
    },
    imgSrc: {
      type: String,
    },
    description:{
      type: String
    },
    race:{
      type: String
    }

  },
  data() {
    return {}
  }
}

</script>

<style scoped>

</style>