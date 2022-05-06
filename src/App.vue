<script setup>
import { RouterView } from "vue-router";
import NavigationBar from "@/components/NavigationBar.vue";
</script>

<template>
  <NavigationBar />

  <router-view></router-view>
</template>

<style>
@import "@/assets/css/styles.css";
</style>
