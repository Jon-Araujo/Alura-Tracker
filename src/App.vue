<template>
  <main>
    <BarraLateral />
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

import BarraLateral from './components/BarraLateral.vue';


export default defineComponent({
  name: 'App',
  components: {
    BarraLateral
  }
});
</script>

<style>

</style>
