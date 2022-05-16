<template>
  <v-row justify="center" align="center">
    <img src="/Blob-1.png" alt="Vuetify.js"  height="30%" width="100%" />
    <v-col cols="12" sm="8" md="12">
      <v-item-group>
        <v-container>
          <v-row align="center">
            <v-col class="d-flex" cols="12" md="1">
             
            </v-col>
            <v-col class="d-flex" cols="12" md="7">
              <NuxtLink to="/emp/EmpReserve">
                <v-btn color="#D43256" elevation="4" icon x-large rounded>
                  <v-icon size="100" dark> mdi-locker-multiple </v-icon>
                </v-btn>
                <p>Reserve locker for student</p>
              </NuxtLink>
            </v-col>
            <v-col class="d-flex" cols="12" md="3">
              <NuxtLink to="/emp/EmpMaintenanceReport">
                <v-btn color="#D43256" elevation="4" icon x-large rounded>
                  <v-icon size="100" dark> mdi-tools </v-icon>
                </v-btn>
                <p>Maintenance request</p>
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
  name: 'EmployeeMainPage',
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