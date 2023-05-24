<script setup>

</script>

<template>
  <select @change="handleSelectChange" class="form-select w-25">
    <option
        v-for="(option, index) in archetypes"
        :value="option[index]"
    >
      {{ option.archetype_name }}
    </option>
  </select>
</template>

<script>
export default {
  data() {
    return {}
  },
  props: {
    archetypes: {
      type: Object,
      required: true
    }
  },
  methods: {
    handleSelectChange() {
      this.$emit('selected-archetype', this.$el.value)
    }
  }

}

</script>

<style scoped>

</style>