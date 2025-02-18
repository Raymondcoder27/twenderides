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

function isRouteActive(routeName: string): {
  return route.name === routeName;
}

function navigate(routeName: string) {
  router.push({name: routeName})
}
</script>

<template>

  <RouterView />
</template>

<style scoped>

</style>
