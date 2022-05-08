<script setup>
import Gallery from "@/components/Detail/Gallery.vue";
import DetailDescription from "@/components/Detail/DetailDescription.vue";
import SideBarDetail from "@/components/Detail/SideBarDetail.vue";
</script>

<template>
  <main>
    <div class="container p-2 mx-auto my-10 max-w-7xl">
      <div class="flex flex-row flex-wrap py-4">
        <main role="main" class="w-full px-4 pt-1 sm:w-2/3 md:w-2/3">
          <h1
            class="mb-2 text-3xl font-bold leading-normal tracking-tight text-gray-900 sm:text-4xl md:text-4xl"
          >
            RoboCrypto UI Kit
          </h1>
          <p class="text-gray-500">Build your next coin startup</p>
          <Gallery />
          <DetailDescription />
        </main>
        <aside class="w-full px-4 sm:w-1/3 md:w-1/3">
          <SideBarDetail />
        </aside>
      </div>
    </div>
  </main>
</template>
