<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="12">
      <v-card>
        <section>
          <v-parallax src="Blob.png" height="900" width="4700">
            <v-layout column align-left justify-center>
              <div class="box">
                <div>
                  <v-img
                    lazy-src="land.png"
                    height="450"
                    width="550"
                    src="land.png"
                    aspect-ratio="1.7"
                    contain
                    class="imgr ml-auto"></v-img>
                </div>
              </div>
              <h1 class="h1mar">Save your Time</h1>
              <h1>& Effort Now!</h1>
              <em class="emstyle"> Locker Management & Reservation System (LMS) </em>
               <v-col> <v-btn v-if="!loggedIn" @click="handleClick" class= "btst" style="color: white" color="#D43256" rounded>Log in</v-btn> </v-col>
            </v-layout>

            <h2 class="vtitel">Who Can Use LMRS?</h2>
            <v-item-group>
              <v-container>
                <v-row>
                  <v-col cols="12" md="4">
                    <v-item>
                      <v-card
                        class="d-flex align-center rounded-xl"
                        height="200"
                        width="300"
                        @click="toggle">
                        <v-scroll-y-transition>
                          <div class="text-h2 flex-grow-1 text-center">
                            <v-icon size="60px" color="#D43256">mdi-cog</v-icon>
                            <p>Managers</p>
                          </div>
                        </v-scroll-y-transition>
                      </v-card>
                    </v-item>
                  </v-col>
                  <v-col cols="12" md="4">
                    <v-item>
                      <v-card
                        class="d-flex align-center rounded-xl"
                        height="200"
                        width="300"
                        @click="toggle">
                        <v-scroll-y-transition>
                          <div class="text-h2 flex-grow-1 text-center">
                            <v-icon size="60px" color="#D43256">mdi-briefcase</v-icon>
                            <p>Employees</p>
                          </div>
                        </v-scroll-y-transition>
                      </v-card>
                    </v-item>
                  </v-col>
                  <v-col cols="12" md="4">
                    <v-item>
                      <v-card
                        class="d-flex align-center rounded-xl"
                        height="200"
                        width="300"
                        @click="toggle">
                        <v-scroll-y-transition>
                          <div class="text-h2 flex-grow-1 text-center">
                            <v-icon size="60px" color="#D43256">mdi-school</v-icon>
                            <p>Student</p>
                          </div>
                        </v-scroll-y-transition>
                      </v-card>
                    </v-item>
                  </v-col>
                </v-row>
              </v-container>
            </v-item-group>
          </v-parallax>
        </section>
      </v-card>
      <v-card> </v-card>
      <v-card>
        <br />
        <h2>Get To Know More About LMSR</h2>
        <v-card-title
          >Lockers Management & Reservation System (LMRS) is a project that solves students’
          reservation problems. Also, solve student affairs employees’ and managers' problems with
          managing and keeping track of the system updat</v-card-title
        >
      
      </v-card>
      <v-card>
        <br />
        <h2>What is our goal</h2>
        <v-card-title
          >Reservations can be a training process, beginning with waiting in long lines, having to
          cancel plans, and wishing on your lucky star that you would finally be able to reserve
          that locker that will make your entire experience as a hard-working student a little
          easier, only to be met with the frustration of not being able to reserve a locker, and
          that's only looking at it from the student perspective. We still need to consider all the
          effort and time that goes in from the student affairs side. All the issues they have to
          deal with seeing that their system is using an Excel sheet only causes all kinds of
          problems like loss of data, unreliable data, and lack of technological
          management.</v-card-title
        >

        <img src="/BlobDown.png" alt="Vuetify.js" height="10%" width="100%" />
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>

<style scoped>
.emstyle {
  font-size: 20px;
  margin-left: 50px;
}
.btst {

  margin-left: 50px;
}
p {
  font-size: 30px;
}
h2 {
  text-align: center;
}

h1 {
  font-size: 80px;
  font-weight: 900;
  margin-left: 50px;
}
.h1mar {
  margin-top: 50px;
}
.vtitel {
  font-size: 50px;
  font-weight: 300;
  color: black;
  text-align: center;
}
.box {
  display: flex;
  align-items: right;
  justify-content: right;
  margin-top: 50px;
}

.box div {
  width: 1500px;
  height: 1px;
}
</style>