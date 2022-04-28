<template>
  <v-row justify="center" align="center">
    <img src="/Blob-1.png" alt="Vuetify.js"  height="30%" width="100%" />
    <v-col cols="12" sm="8" md="12">
      <v-item-group>
        <v-container>
          <v-row align="center">
            <v-col cols="10" md="2">
              <NuxtLink to="/manager/ManDashboard">
                <v-btn color="#D43256" elevation="4" icon x-large rounded>
                  <v-icon size="100" dark> mdi-monitor-dashboard </v-icon>
                </v-btn>
                <p>Dashboard</p>
              </NuxtLink>
            </v-col>
            <v-col cols="10" md="2">
              <NuxtLink to="/manager/ManReserve">
                <v-btn color="#D43256" elevation="4" icon x-large rounded>
                  <v-icon size="100" dark> mdi-locker </v-icon>
                </v-btn>
                <p>Reserve locker for studnet</p>
              </NuxtLink>
            </v-col>
            <v-col cols="10" md="2">
              <NuxtLink to="/manager/ManGenReport">
                <v-btn color="#D43256" elevation="4" icon x-large rounded>
                  <v-icon size="100" dark> mdi-file-chart </v-icon>
                </v-btn>
                <p>Generate reports</p>
              </NuxtLink>
            </v-col>
            <v-col cols="10" md="2">
              <NuxtLink to="/manager/ManModifyLockerInfo">
                <v-btn color="#D43256" elevation="4" icon x-large rounded>
                  <v-icon size="100" dark> mdi-locker-multiple </v-icon>
                </v-btn>
                <p>Modify lockers info</p>
              </NuxtLink>
            </v-col>
            <v-col cols="10" md="2">
              <NuxtLink to="/manager/ManModifyBuildingInfo">
                <v-btn color="#D43256" elevation="4" icon x-large rounded>
                  <v-icon size="100" dark> mdi-domain </v-icon>
                </v-btn>
                <p>Modify buildings info</p>
              </NuxtLink>
            </v-col>
          </v-row>
        </v-container>
      </v-item-group>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'ManagerMainPage',
}
</script>
<style scoped>
a {
  text-decoration: none;
  color: black;
  font-family: 'Poppins';
  font-size: 30px;
}
.v-btn {
  border-radius: 50%;
  width: 150px;
  height: 150px;
}
</style>