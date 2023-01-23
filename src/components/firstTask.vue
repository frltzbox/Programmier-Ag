<template>
  <section>
  <q-btn @click="getAvatar">
    Neues Profil
  </q-btn>

    <q-card v-if="userData">
      {{ userData }}
        <q-img :src="userData.picture.medium"  spinner-color="white" style="height: 140px; max-width: 150px" />
      <q-card-section>


      </q-card-section>
    </q-card>

  </section>
</template>

<script setup>

import { ref } from "vue";

import axios from "axios"

const emit = defineEmits(['currentUser'])
const userData = ref(null)


async function getAvatar() {
  let response = await axios.get("https://randomuser.me/api/")
  userData.value = response.data.results[0]
  console.log(response)
  emit("currentUser", response.data.results[0])
}

</script>

<style></style>
