<script setup>

</script>

<template>
  <select class="form-select">
    <option v-for="(option, index) in store.archetypes" :value="option[index]">{{ option.archetype_name }}</option>
  </select>
</template>

<script>
export default {
  data() {
    return {
      options: ['option1', 'option2', 'option3'],
      selectedOption: "xaxxa"
    }
  },
  props: {
    store: {
      type: Object,
      required: true
    }
  }
}

</script>

<style scoped>

</style>