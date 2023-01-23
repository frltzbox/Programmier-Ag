<template>
  <ul>
    <div class="liste" v-for="(item, i) in produkt" :key="i">
      <li class="preis">Preis: {{ item.preis }} <br /></li>
      <li class="name">Name: {{ item.name }}</li>
    </div>
  </ul>
</template>

<script setup>
const props = defineProps({
  produkt: Array,
});
</script>

<style>
body {
  background: green;
}
.liste {
  background: rgb(85, 85, 186);
  width: 11rem;
  border-style: solid;
  border-radius: 30px;
  padding: 2em;
  margin: 2em;
}
.preis {
  left: 30px;
}
.name {
  margin: auto;
}
</style>
