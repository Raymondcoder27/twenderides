<script setup lang="ts">
import {ref, type Ref } from 'vue';
import {useRoute } from 'vue-router';
import router from '@/router';
import Home from '@/views/Home.vue';
import {title} from 'process';
</script>

<template>

  <RouterView />
</template>

<style scoped>

</style>
