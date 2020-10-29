<template>
  <v-footer
    dark
    padless
  >
    <!-- <v-card
      flat
      tile
      class="white--text text-center"
      style="background-color: #272727;"
    >
      <v-card-text>
        <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-4 white--text"
          icon
        >
          <v-icon size="24px">
            {{ icon }}
          </v-icon>
        </v-btn>
      </v-card-text>

      <v-card-text class="white--text pt-0">
        
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>Sthapatiknirman</strong>
      </v-card-text>
    </v-card> -->
    <v-row
      justify="center"
      no-gutters
    >
      <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-4 pt-4 white--text"
          icon
        >
          <v-icon size="28px">
            {{ icon }}
          </v-icon>
        </v-btn>
        <v-col
        class="py-4 text-center white--text"
        cols="12"
      >
        <strong>Sthapatik Nirman. </strong>Flat-D4 ,House- 37,road-27, Block-A,banani, Dhaka-1213    email: sthapotiknirman@gmail.com
      </v-col>
      <v-divider></v-divider>
      <v-col
        class="py-4 text-center white--text"
        cols="12"
      >
        @{{ new Date().getFullYear() }} — <strong>Sthapatik Nirman. </strong> All rights reserved.


      </v-col>
    </v-row>
  </v-footer>
</template>

<script>
export default {
    data: () => ({
      icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-linkedin',
        'mdi-instagram',
      ],

      items: [
      {
        name: "Product",
        tags: [
          {
            urlname: "Create Websites",
            url: "#!"
          },
          {
            urlname: "Secure Cloud Hosting",
            url: "#!"
          },
          {
            urlname: "Engage Your Audience",
            url: "#!"
          },
          {
            urlname: "Website Support",
            url: "#!"
          }
        ]
      },
      { name: "Company", 
       tags: [
         { urlname: "About", url: "#!" },
         { urlname: "Careers", url: "#!"},
         { urlname: "Support", url: "#!"},
         { urlname: "Pricing", url: "#!"},
         { urlname: "FAQ", url: "#!"}
       ] 
      },
      { name: "Resources", 
       tags: [
         { urlname: "Blog", url: "#!" },
         { urlname: "eBooks", url: "#!" },
         { urlname: "Whitepapers", url: "#!" },
         { urlname: "Comparison Guide", url: "#!" },
         { urlname: "Website Grader", url: "#!" }
       ] 
      },
      { name: "Get Help", 
       tags: [
         { urlname: "Help Center", url: "#!" },
         { urlname: "Contact Us", url: "#!" },
         { urlname: "Privacy Policy", url: "#!" },
         { urlname: "Terms", url: "#!" },
         { urlname: "Login", url: "#!" }
       ]
      }
    ]
    }),
}
</script>

<style>

</style>