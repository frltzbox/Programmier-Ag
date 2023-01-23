<template>
  <section>
    <div class="card-container">
      <q-card v-if="userData">

          <q-img :src="userData.picture.large"  spinner-color="white" style="height: 140px; max-width: 150px" />

            <q-card-section>
              {{ userData.name.title}}
              {{ userData.name.first}}
              {{ userData.name.last}}
            </q-card-section>

            <q-card-section>
              {{ userData.location.street.number }}
              {{ userData.location.street.name}},
              {{ userData.location.city}},
              {{ userData.location.state}},
              {{ userData.location.country}}
            </q-card-section>

            <q-card-section>
            {{ userData.email }}
            </q-card-section>
      </q-card>
    </div>
    <div class="btn-container">
      <q-btn @click="getAvatar">
        Neues Profil
      </q-btn>
  </div>

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

<style>
.card-container{
  margin-top: 10px;
  width:auto;
  height:40vh;
}
.btn-container{
line-height: 200px;
  margin: auto;
  text-align: center;
  width: 300px;
  height: 200px;
  padding-top: 100px;
}

.q-card{
  width: 25%;
  height: auto;
  margin: auto;
  border: 3px solid green;
  padding: 10px;
}
</style>
