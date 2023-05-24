<script setup>
import 'bootstrap/dist/css/bootstrap.css';
import {AppHeader, AppMain} from "./components/index.js";

</script>

<template>
  <div class="page-wrapper">
    <app-header class="header" r/>
    <app-main class="main"/>
  </div>
</template>

<style lang="sass">
@use "./main.sass" as *

.main
  background-color: $main_container-color
  flex-grow: 1

.page-wrapper
  height: 100vh
  display: flex
  flex-direction: column
</style>
