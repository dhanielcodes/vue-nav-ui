<template>
  <div :class="{ container: navConfig.whitespace, open: open }">
    <div class="nav">
      <slot></slot>
      <div
        class="links"
        :class="{
          open: open,
          bottom: navConfig.responsivePosition == 'bottom',
          top: navConfig.responsivePosition == 'top',
        }"
      >
        <router-link
          class="link"
          v-for="(navName, idx) in navLinks"
          :key="idx"
          :to="navName.path"
          >{{ navName.name }}</router-link
        >
        <a class="linkBtn" :href="btnConfig.btnUrl" v-if="btnConfig.btnLink">
          <button>
            <slot name="btnAppend"></slot>
            <p>{{ btnConfig.btnText }}</p>
            <slot name="btnPrepend"></slot>
          </button>
        </a>
      </div>
      <div :class="{ open: open }" class="toggle" @click="open = !open">
        <svg
          width="28"
          height="28"
          viewBox="0 0 28 28"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <rect
            x="28"
            y="12"
            width="4"
            height="28"
            rx="2"
            transform="rotate(90 28 12)"
            :fill="navConfig.linkColor"
          />
          <rect
            x="16"
            y="28"
            width="4"
            height="28"
            rx="2"
            transform="rotate(-180 16 28)"
            :fill="navConfig.linkColor"
          />
        </svg>
      </div>
      <a class="navBtn" :href="btnConfig.btnUrl" v-if="btnConfig.btnLink">
        <button>
          <slot name="btnAppend"></slot>
          <p>{{ btnConfig.btnText }}</p>
          <slot name="btnPrepend"></slot>
        </button>
      </a>
    </div>
  </div>
  <div class="excess"></div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Nav",
  props: {
    navLinks: {
      type: Array,
      required: true,
    },
    navConfig: {
      type: Object,
      required: true,
    },
    btnConfig: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      open: false,
    };
  },
});
</script>

<style scoped>
.excess {
  height: 122px;
  width: 100%;
  display: none;
}
.container {
  padding: 20px;
}
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 1400px;
  margin: auto;
  border-radius: v-bind("navConfig.navBorderRadius");
  padding: 16px;
  background: v-bind("navConfig.navBg");
}
@media (max-width: 1400px) {
  .nav {
    width: 100%;
  }
}
.link {
  text-decoration: none;
  margin: 0 20px;
  font-family: v-bind("navConfig.linkFont");
  color: v-bind("navConfig.linkColor");
}
button {
  border-radius: v-bind("btnConfig.btnBorderRadius");
  background: v-bind("btnConfig.btnBg");
  color: v-bind("btnConfig.btnTextColor");
  font-family: v-bind("navConfig.linkFont");
  display: flex;
  justify-content: space-between;
  align-items: center;
  border: none;
  padding: 10px 20px;
  border: v-bind("btnConfig.btnBorderWidth") solid v-bind("btnConfig.btnBorderColor");
  cursor: pointer;
  outline: none;
  font-size: 18px;
}
button p {
  margin: 0 10px;
}
.right {
  flex-direction: row;
}
.linkBtn {
  display: none;
}
.left {
  flex-direction: row-reverse;
}
.toggle {
  display: none;
}
@media (max-width: 790px) {
  .excess {
    display: block;
  }
  .container {
    height: 100vh;
    position: fixed;
    left: 0;
    pointer-events: none;
    top: 0;
    width: 100%;
    transition: all 0.3s;
  }
  .container.open {
    pointer-events: all;
    background: rgba(0, 0, 0, 0.337);
    backdrop-filter: blur(4px);
  }
  .toggle {
    display: block;
    padding: 10px;
    background: v-bind("navConfig.navBg");
    border-radius: 100%;
    width: 50px;
    height: 50px;
    cursor: pointer;
    transform: rotate(0deg);
    pointer-events: all;
    transition: all 0.3s;
  }
  .toggle svg {
    width: 100%;
    height: 100%;
  }
  .toggle.open {
    transform: rotate(45deg);
  }
  .nav {
    position: relative;
    background: none;
    justify-content: space-between;
  }
  .links {
    position: fixed;
    left: 50%;
    background: v-bind("navConfig.navBg");
    display: flex;
    flex-direction: column;
    padding: 40px 30px;
    width: 90%;
    margin-top: 80px;
    border-radius: 20px;
    transform: translateY(50px) translateX(-50%);
    pointer-events: none;
    transition: all 0.3s;
    opacity: 0;
  }
  .links.open {
    opacity: 1;
    transform: translateY(0px) translateX(-50%);
    pointer-events: all;
  }
  .links.bottom {
    bottom: 0;
    border-radius: 20px 20px 0px 0px;
  }
  .links.top {
    top: 40px;
  }
  .links .link {
    margin: 15px 0;
  }
  .navBtn {
    display: none;
  }
  .linkBtn {
    display: block;
    margin-top: 20px;
  }
}
</style>
