<template>
  <v-app light>
    <v-toolbar class="white">
      <v-toolbar-side-icon>
        <img :src="imageLink.logo" alt="Vuetify.js" height="30" width="45" />
      </v-toolbar-side-icon>
      <v-toolbar-title class="mx-0" v-text="title"></v-toolbar-title>
      <p>LMS</p>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn flat>Home</v-btn>
        <!--<v-btn flat>Blog</v-btn>-->
        <v-btn flat class="pink lighten-3">About</v-btn>
        <v-btn flat class="pink lighten-3">Contact</v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-content>
      <section>
        <v-parallax src="BlobTop.png" max-height="200" max-width="100" aspect-ratio="1.7" contain>
          <v-layout column align-left justify-center>
            <div class="headline white--text mb-3 text-xs-center">
             Save your time & Effort Now! 
            </div>
            <em
              >Locker Management & Reservation System (LMS)</em
            >
            <v-btn style="color: white" color="#D43256" rounded>log in</v-btn>
          </v-layout>
        </v-parallax>
      </section>

      <section>
        <v-container grid-list-md>
          <v-layout row wrap>
            <v-flex xs12 text-xs-center class="mt-5">
              <div class="headline">Are you amazed? Stay tuned!</div>
              <br />
              <div>
                Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptate quidem odit,
                quas alias voluptas tempora repellat vero. Eius iste, voluptas expedita dolor eaque
                optio impedit sint, facere molestiae, reprehenderit enim!
              </div>
            </v-flex>
            <v-flex xs8 offset-xs2>
              <v-card class="elevation-0 transparent">
                <v-card-text>
                  <v-flex v-if="!subscribed" xs12>
                    <v-text-field
                      v-model="email"
                      box
                      label="Email address"
                      :rules="emailRules"
                      hint="Enter your email!"
                      persistent-hint></v-text-field>
                  </v-flex>
                  <v-flex v-if="!subscribed" xs12>
                    <v-text-field box multi-line label="Bio and curiosities"></v-text-field>
                  </v-flex>
                  <v-flex v-if="!subscribed" xs12 class="text-xs-center">
                    <v-btn class="blue lighten-2 mb-5" dark large @click="subscribe"
                      >Get in touch</v-btn
                    >
                  </v-flex>
                  <v-flex v-if="subscribed" xs12 class="text-xs-center">
                    <v-btn class="green lighten-2 mb-5" dark large>Welcome on board!</v-btn>
                  </v-flex>
                </v-card-text>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </section>

      <section>
        <v-parallax :src="imageLink.social_cover" height="380">
          <v-layout column align-center justify-center>
            <div class="headline white--text mb-3 text-xs-center">
              We are dropping cool news and opportunities on socials
            </div>
          </v-layout>
          <v-layout justify-space-around justify-center>
            <v-icon x-large dark>fab fa-facebook-f</v-icon>

            <v-icon x-large dark>fab fa-twitter</v-icon>

            <v-icon x-large dark>fab fa-reddit-alien</v-icon>

            <v-icon x-large dark>fab fa-instagram</v-icon>

            <v-icon x-large dark>fab fa-discord</v-icon>
          </v-layout>
        </v-parallax>
      </section>

      <section>
        <v-container grid-list-xl>
          <v-layout row wrap justify-center class="my-5">
            <v-flex xs12 sm4>
              <v-card class="elevation-0 transparent">
                <v-card-title primary-title class="layout justify-center">
                  <div class="headline">Company info</div>
                </v-card-title>
                <v-card-text>
                  Lorem ipsum dolor sit amet consectetur, adipisicing elit. Impedit temporibus
                  officiis, hic distinctio aut neque facere, quas incidunt atque eveniet iusto
                  voluptates veniam sint illum provident! Ipsam quod eaque quaerat.
                </v-card-text>
              </v-card>
            </v-flex>
            <v-flex xs12 sm4 offset-sm1>
              <v-card class="elevation-0 transparent">
                <v-card-title primary-title class="layout justify-center">
                  <div class="headline">We are hiring</div>
                </v-card-title>
                <v-card-text>
                  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Cum itaque ipsum dolore
                  beatae aliquam blanditiis vel corporis esse consequatur, explicabo ex, nostrum
                  culpa rerum. Ex facilis porro repellendus ratione earum!
                </v-card-text>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </section>

      <section>
        <v-container>
          <v-layout>
            <v-flex xs12 class="text-xs-center">
              <img height="200px" :src="imageLink.logo" />
            </v-flex>
          </v-layout>
        </v-container>
      </section>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      title: 'Locker Managment System',
      imageLink: {
        main: 'https://firebasestorage.googleapis.com/v0/b/endorfinevue.appspot.com/o/assets%2FNight-Club-Clubbing-Jobs-Abroad2.jpg?alt=media&token=82bbda7d-5df4-430b-9217-adaf1c8485c5',
        sub_main:
          'https://firebasestorage.googleapis.com/v0/b/endorfinevue.appspot.com/o/assets%2FNight-Club-Clubbing-Jobs-Abroad2.jpg?alt=media&token=82bbda7d-5df4-430b-9217-adaf1c8485c5',
        logo: 'logo.png',
        social_cover:
          'https://firebasestorage.googleapis.com/v0/b/endorfinevue.appspot.com/o/assets%2Fo-NIGHTCLUB-facebook.jpg?alt=media&token=cefc5c4c-9714-41da-9c22-f63caf5e89a4',
      },
      email: '',
      emailRules: [
        (v) => {
          return !!v || 'E-mail is required'
        },
        (v) => /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid',
      ],
      subscribed: false,
    }
  },

  computed: {
    imgHeight() {
      const offset = 320
      return this.pageHeight - offset
    },
  },

  mounted() {
    this.calculateHeight()
  },
  methods: {
    subscribe() {
      this.subscribed = !this.subscribed
    },
  },
}
</script>

<style scoped>
.finedTitle {
  font-weight: 900;
  text-shadow: 2px 2px #000000;
}

.social-icon {
  font-size: 21px;
  color: white;
}
</style>
