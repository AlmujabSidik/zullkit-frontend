<script setup>
import { onMounted, computed } from "vue";
import { useUserStore } from "@/stores/user";

import Logo from "@/components/Navbar/logo.vue";
import NavigationLink from "@/components/Navbar/NavigationLink.vue";
import UserInfo from "@/components/Navbar/UserInfo.vue";
import UserLogin from "@/components/Navbar/UserLogin.vue";

const userStore = useUserStore();
const user = computed(() => userStore.getUser);
const isLoggedIn = computed(() => userStore.isLoggedIn);

onMounted(() => {
  userStore.fetchUser();
});
</script>

<template>
  <nav class="bg-white border-gray-200 px-2 sm:px-4 py-2.5 rounded dark:bg-gray-800">
    <div class="container flex flex-wrap items-center justify-between mx-auto my-2">
      <Logo />
      <div v-if="isLoggedIn">
        <UserInfo />
      </div>
      <UserLogin v-else />
      <NavigationLinks />
    </div>
  </nav>
</template>
