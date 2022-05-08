<script setup>
import { ref } from "vue";
import ItemsCards from "@/components/homepage/NewItems/ItemsCards.vue";
import { RouterLink } from "vue-router";

const Items = ref([
  { id: 1, title: "Mobile UI Kit", image: "items-1.jpg", detail: "Mobile UI Kit" },
  {
    id: 2,
    title: "Online Doctor Consultation",
    image: "items-2.jpg",
    detail: "Website UI Kit ",
  },
  { id: 3, title: "Banking Crypto", image: "items-3.jpg", detail: "Mobile UI Kit" },
]);
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12">
    <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">New Items</h2>
    <div class="flex flex-wrap -mx-1 lg:-mx-4">
      <ItemsCards
        v-for="item in Items"
        :key="item.id"
        :id="item.id"
        :title="item.title"
        :image="item.image"
        :detail="item.detail"
      />
    </div>
  </div>
</template>
