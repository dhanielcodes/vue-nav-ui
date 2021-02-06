<template>
  <div class="home">
    <Nav />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { Nav } from "@/components";

export default defineComponent({
  name: "Home",
  components: {
    Nav,
  },
});
</script>
