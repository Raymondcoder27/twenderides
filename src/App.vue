<script setup lang="ts">
import {ref, type Ref } from 'vue';
import {useRoute } from 'vue-router';
import router from '@/router';
import Home from '@/views/Home.vue';
import {title} from 'process';

const name = ref<string>("Raymond");
const age = ref<number>(25);

const route = useRoute();

type SideMenuLink  = {
  name: string;
  label: string;
}

const SideMenu: Ref<Array<SideMenuLink>> = ref([
  {name: 'home', label: 'Home'},
  {name: 'about', label: 'About'},
  {name: 'contact', label: 'Contact'},
]);

function isRouteActive(routeName: string) {
  return route.name === routeName;
}

function navigate(routeName: string) {
  router.push({name: routeName})
}
</script>

<template>
  <header>
    <div class="w-full bg-black py-7 text-center flex justify-center items-center top-0 fixed">
      <div class="absolute left-0 right-0 flex justify-center text-white font-bold">
        <h3>Twende Rides</h3>
      </div>
    </div>
  </header>
  <RouterView />
</template>

<style scoped>

</style>
