<template>
  <section>

  <firstComponent :produkt="produkt"> </firstComponent>
  <firstTask />
</section>
</template>

<script setup>
import { ref } from "vue";

import firstTask from "components/firstTask.vue"

const userData = ref(null)
</script>
<style>

</style>
