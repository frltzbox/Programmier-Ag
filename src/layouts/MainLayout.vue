<template>
  <section>
  <essential-link></essential-link>
  <firstTask></firstTask>
  </section>
</template>

<script>
import { defineComponent } from "vue";
import EssentialLink from "components/EssentialLink.vue";
import firstTask from "../components/firstTask.vue";

export default defineComponent({
  name: "MainLayout",

  components: {
    EssentialLink,
    firstTask
  },

});


</script>
