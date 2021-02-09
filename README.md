<img src="https://res.cloudinary.com/devdaniel/image/upload/v1612899979/Frame_12_xohomk.png"/>

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
      <img class="img" src="logo" alt="" srcset="" /> <!-- A slot For your project Logo -->
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
     /* FOR YOUR NAVIGATION LINKING NAMES AND PATHS */ 
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

    /* FOR CONFIGURING THE STYLING OF YOUR NAVIGATION */
    const navConfig = ref({
      whitespace: true, /* GIVES PADDING TO YOUR NAV, IF SET TO FALSE, REMOVES PADDING */
      navBg: "#FAFAFA", /* BACKGROUND COLOR OF YOUR NAV  */
      navBorderRadius: "30px", /* BORDER RADIUS OF YOUR NAV */
      linkFont: "poppins", /* FONT FAMILY OF YOUR NAV */
      linkColor: "black", /* FONT COLOR OF YOUR NAV */
      responsivePosition: "top or bottom", /* FOR CHANGING THE POSITION OF YOUR NAV WHEN RESPONSIVE. BOTTOM or TOP | The only two options */
    });

     /* FOR NAV BUTTON CONFIGURATION */
    const btnConfig = ref({
      btnLink: true, /* FOR INITIALIZING NAV BUTTON USAGE, IF SET TO FALSE, REMOVES THE NAV BUTTON  */
      btnUrl: "https://dhaniel.disha.page", /* LINK URL OF YOUR NAV BUTTON */
      btnText: "Download app", /* NAV BUTTON TEXT */
      btnBg: "#40269E", /* BACKGROUND COLOR OF YOUR NAV BUTTON  */
      btnTextColor: "white", /* FONT COLOR OF YOUR NAV BUTTON*/
      btnBorderWidth: "0", /* BORDER WIDTH OF YOUR NAV BUTTON */
      btnBorderColor: "black", /* BORDER COLOR OF YOUR NAV BUTTON */
      btnBorderRadius: "20px", /* BORDER RADIUS OF YOUR NAV BUTTON */
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
      <img class="img" src="logo" alt="" srcset="" /> <!-- A slot For your project Logo -->
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
            /* FOR YOUR NAVIGATION LINKING NAMES AND PATHS */ 
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
                whitespace: true, /* GIVES PADDING TO YOUR NAV, IF SET TO FALSE, REMOVES PADDING */
                navBg: "#FAFAFA", /* BACKGROUND COLOR OF YOUR NAV  */
                navBorderRadius: "30px", /* BORDER RADIUS OF YOUR NAV */
                linkFont: "poppins", /* FONT FAMILY OF YOUR NAV */
                linkColor: "black", /* FONT COLOR OF YOUR NAV */
                responsivePosition: "top or bottom", /* FOR CHANGING THE POSITION OF YOUR NAV WHEN RESPONSIVE. BOTTOM or TOP | The only two options */
            },
            btnConfig: {
                btnLink: true, /* FOR INITIALIZING NAV BUTTON USAGE, IF SET TO FALSE, REMOVES THE NAV BUTTON  */
                btnUrl: "https://dhaniel.disha.page", /* LINK URL OF YOUR NAV BUTTON */
                btnText: "Download app", /* NAV BUTTON TEXT */
                btnBg: "#40269E", /* BACKGROUND COLOR OF YOUR NAV BUTTON  */
                btnTextColor: "white", /* FONT COLOR OF YOUR NAV BUTTON*/
                btnBorderWidth: "0", /* BORDER WIDTH OF YOUR NAV BUTTON */
                btnBorderColor: "black", /* BORDER COLOR OF YOUR NAV BUTTON */
                btnBorderRadius: "20px", /* BORDER RADIUS OF YOUR NAV BUTTON */
            }
        }
    }
};
</script>
```

## Responsive Position

### Top position

```vue
navConfig: {
    //
    responsivePosition: "top",
}
```

<img src="https://res.cloudinary.com/devdaniel/image/upload/v1612909704/e_kmc4u8.png"/>


### Bottom position

```vue
navConfig: {
    //
    responsivePosition: "bottom",
}
```

<img src="https://res.cloudinary.com/devdaniel/image/upload/v1612909709/ee_j6clb3.png"/>


# Add icon to nav button

```vue
//Adds icon before the text
<template #btnAppend>
        <img class="img" src="icon" alt="" srcset="" />
</template>



//Adds icon after the text
<template #btnPrepend>
        <img class="img" src="icon" alt="" srcset="" />
</template>
````


# FEEL FREE TO CONTRIBUTE : )

## Clone
```
git clone https://github.com/dhanielcodes/vue-nav-ui.git
```
## Project setup
```
yarn install
```
## Compiles and hot-reloads for development
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
