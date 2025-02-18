<script setup lang="ts">
import { ref, type Ref } from "vue";
import { useRoute } from "vue-router";
// import router from "@/router";
// import Home from "@/views/Home.vue";

const name = ref<string>("Raymond");
const age = ref<number>(25);

const route = useRoute();

type SideMenuLink = {
  name: string;
  label: string;
};

const SideMenu: Ref<Array<SideMenuLink>> = ref([
  { name: "home", label: "Home" },
  { name: "about", label: "About" },
  { name: "contact", label: "Contact" },
]);

function isRouteActive(routeName: string) {
  return route.name === routeName;
}

function navigate(routeName: string) {
  router.push({ name: routeName });
}
</script>

<template>
  <header>
    <div
      class="w-full bg-black py-7 text-center flex justify-center items-center top-0 fixed"
    >
      <div
        class="absolute left-0 right-0 flex justify-center text-white font-bold"
      >
        <h3>Twende Rides</h3>
      </div>

      <div class="bg-gray-100 mr-3 rounded-md p-1 absolute right-0">
        <h3 class="text-gray-500 font-mono text-sm font-semibold">
          {{ name }}, {{ age }}
        </h3>
      </div>
    </div>
  </header>
  <RouterView />
</template>

<style scoped>
</style>
