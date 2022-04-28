<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" :mini-variant="miniVariant" fixed app>
      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to" router exact>
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer padless>
      <v-col class="text-center" cols="12">
        {{ new Date().getFullYear() }} —
        <strong>All copyrights reserved to group M 15 </strong>
      </v-col>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      drawer: false,
      items: [
        {
          icon: 'mdi-home',
          title: 'Home',
          to: '/',
        },
        {
          icon: 'mdi-information-outline',
          title: 'About',
          to: '/AboutUs',
        },
        {
          icon: 'mdi-forum',
          title: 'Contact',
          to: '/ContactUs',
        },
        {
          icon: 'mdi-school',
          title: 'Student',
          to: '/stu',
        },
        {
          icon: 'mdi-briefcase',
          title: 'Employee',
          to: '/emp',
        },
        {
          icon: 'mdi-human-male',
          title: 'Manager',
          to: '/manager',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Locker Managment and Reservation System',
    }
  },
}
</script>
<style>
#app {
  background-color: #fdfaf6;
}
</style>