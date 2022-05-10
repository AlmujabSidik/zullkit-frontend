<script setup>
import { ref, onMounted } from "vue";
import ItemsCards from "@/components/homepage/NewItems/ItemsCards.vue";
import axios from "axios";

const Items = ref([]);

async function getItemsData() {
  try {
    const response = await axios.get(
      "https://zullkit-backend.buildwithangga.id/api/products"
    );
    Items.value = response.data.data.data;
  } catch (error) {
    console.error(error);
  }
}

onMounted(() => {
  getItemsData();
});
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12">
    <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">New Items</h2>
    <div class="flex flex-wrap -mx-1 lg:-mx-4">
      <ItemsCards
        v-for="item in Items"
        :key="item.id"
        :id="item.id"
        :title="item.name"
        :image="item.thumbnails"
        :detail="item.category.name"
      />
    </div>
  </div>
</template>
