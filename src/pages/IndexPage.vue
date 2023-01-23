<template>
  <section>

  <firstComponent :produkt="produkt"> </firstComponent>
  <firstTask @currentUser="val => userData = val"/>


    <q-card>
      <q-card-section>
    {{ userData }}

      </q-card-section>
    </q-card>
</section>
</template>

<script setup>
import { ref } from "vue";

import firstTask from "components/firstTask.vue"

const userData = ref(null)
</script>
