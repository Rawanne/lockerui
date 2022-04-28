<template>
  <v-container fluid>
    <form action="">
      <v-row align="center">
        <v-col class="d-flex" cols="8" sm="4">
          <v-select :items="topic" label="Topic filter"></v-select>
        </v-col>
        <v-col class="d-flex" cols="8" sm="4">
          <v-select :items="duration" label="Duration filter"></v-select>
        </v-col>
      </v-row>
      <v-btn rounded class="mr-4" @click="submit"> Show Results </v-btn>
    </form>
    <br />
    <v-divider></v-divider>
    <br /><br />
    <v-row align="center">
      <v-card class="mx-auto" max-width="800" elevation="2">
        <v-card-title>
          <h2 class="text-h4">Search results:</h2>
          <v-spacer></v-spacer>
        </v-card-title>
        <v-card-text>
         Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quaerat iste repudiandae, fuga impedit dolore, fugiat nulla, commodi quam nam voluptate placeat ducimus! Neque, adipisci repellat suscipit eaque nulla facere sit?
        </v-card-text>
        <v-divider class="mx-4"></v-divider>
        <v-card-text>
          <v-chip-group active-class="deep-purple--text text--accent-4">
            <v-chip>Number of buildings: 150</v-chip>
            <v-chip>Number of lockers: 120</v-chip>
            <v-chip>Duration time: 20 w</v-chip>
          </v-chip-group>
        </v-card-text>
        <v-card-actions>
          <v-btn  class="white--text" color="#FE9593"> Delete report </v-btn>
          <v-btn  class="white--text" color="#FDBFA8"> Save report </v-btn>
        </v-card-actions>
      </v-card>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'ManGenReport',
  data: () => ({
    topic: ['Buildings', 'Lockers', 'Payments'],
    duration: ['Week', 'Month', 'Semester', 'Year'],
  }),
  methods: {
    submit() {
      this.$v.$touch()
    },
  },
}
</script>
