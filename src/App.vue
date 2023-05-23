<script setup>
import 'bootstrap/dist/css/bootstrap.css';
import {AppHeader, AppMain} from "./components/index.js";

</script>

<template>
  <div >
    <app-header class="header" r/>
    <app-main class="main"/>
  </div>
</template>

<style lang="sass">
@use "./main.sass" as *

.main
  background-color: $main_container-color

</style>
