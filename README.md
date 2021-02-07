# Vue Navigation UI

###### Note: Package only compatible with new vue releases (vue 3 | vitejs)

## Installation
```
npm install vue-nav-ui
```

```vue
import Nav from "vue-nav-ui";

export default {
  components: {
    Nav
  }
}
```
## Basic Usage Configuration
### Composition-api

```vue
<template>
  <div>
    <Nav :navLinks="navLinks" :navConfig="navConfig" :btnConfig="btnConfig">
      <img class="img" src="../assets/logo.png" alt="" srcset="" />
    </Nav>
  </div>
</template>

<script>
import Nav from "vue-nav-ui";

export default {
  components: {
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
};
</script>
```

### Options-api

```vue
<template>
  <div>
    <Nav :navLinks="navLinks" :navConfig="navConfig" :btnConfig="btnConfig">
      <img class="img" src="../assets/logo.png" alt="" srcset="" />
    </Nav>
  </div>
</template>

<script>
import Nav from "vue-nav-ui";

export default {
  components: {
    Nav,
  },
  data(){
        return {
            navLinks: [
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
            ],
            navConfig: {
                whitespace: true,
                navBg: "#FAFAFA",
                navBorderRadius: "30px",
                linkFont: "poppins",
                linkColor: "black",
            },
            btnConfig: {
                btnLink: true,
                btnUrl: "https://dhaniel.disha.page",
                btnText: "Download app",
                btnBg: "#40269E",
                btnTextColor: "white",
                btnBorderWidth: "0",
                btnBorderColor: "black",
                btnBorderRadius: "20px",
            }
        }
    }
};
</script>
```










## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
