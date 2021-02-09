<template>
  <div class="home">
    <Nav :navLinks="navLinks" :navConfig="navConfig" :btnConfig="btnConfig">
      <img class="img" src="../assets/logo.png" alt="" srcset="" />
      <template #btnAppend>
        <img class="img" src="../assets/logo.png" alt="" srcset="" />
      </template>
    </Nav>
    <h1>Hello</h1>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
//import VueNavUI from "vue-nav-ui";
import { Nav } from "../components";

export default defineComponent({
  name: "Home",
  components: {
    //VueNavUI,
    Nav,
  },
  setup() {
    const navLinks = ref([
      {
        name: "Home",
        path: "/",
      },
      {
        name: "About",
        path: "/about",
      },
      {
        name: "FAQs",
        path: "/faqs",
      },
      {
        name: "More",
        path: "/more",
      },
      {
        name: "Media",
        path: "/media",
      },
    ]);
    const navConfig = ref({
      whitespace: true,
      navBg: "#FAFAFA",
      navBorderRadius: "30px",
      linkFont: "poppins",
      linkColor: "black",
      responsivePosition: "top",
    });

    const btnConfig = ref({
      btnLink: true,
      btnUrl: "https://dhaniel.disha.page",
      btnText: "Download app",
      btnBg: "#40269E",
      btnTextColor: "white",
      btnBorderWidth: "0",
      btnBorderColor: "black",
      btnBorderRadius: "20px",
    });

    return { navLinks, btnConfig, navConfig };
  },
});
</script>
<style scoped>
.home {
  height: 100vh;
}
.img {
  width: 30px;
}
.btnImg {
  width: 100%;
}
</style>
