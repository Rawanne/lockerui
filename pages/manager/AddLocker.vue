<template>
  <v-container fluid>
    <form action="">
      <v-row align="center">
        <v-col class="d-flex" cols="12" sm="4">
          <v-text-field label="Enter Building number" placeholder="1"></v-text-field>
        </v-col>
        <v-col class="d-flex" cols="12" sm="4">
          <v-text-field label="Enter Locker Number" placeholder="1"></v-text-field>
        </v-col>
      </v-row>
      <v-row align="center">
        <v-card class="mx-auto" max-width="420" elevation="2">
          <v-card-title>
            <h2 class="text-h4">New Locker information:</h2>
            <v-spacer></v-spacer>
          </v-card-title>
          <v-card-text>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quaerat iste repudiandae, fuga
            impedit dolore, fugiat nulla, commodi quam nam voluptate placeat ducimus! Neque,
            adipisci repellat suscipit eaque nulla facere sit?
          </v-card-text>
          <v-divider class="mx-4"></v-divider>
          <v-card-text>
            <v-chip-group active-class="deep-purple--text text--accent-4">
              <v-chip>Number of buildings: 150</v-chip>
              <v-chip>Number of lockers: 120</v-chip>
            </v-chip-group>
          </v-card-text>
          <v-card-actions>
            <v-row justify="center">
              <v-dialog v-model="dialog" persistent max-width="450">
                <template #activator="{on, attrs}">
                  <v-btn color="#D43256" rounded dark v-bind="attrs" v-on="on">confirm</v-btn>
                </template>
                <v-card>
                  <v-card-title class="text-h5">
                    Are you sure about this information?
                  </v-card-title>
                  <v-card-text> you will add new Locker if you clicked Yes. </v-card-text>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn color="red darken-1" text @click="dialog = false"> Cancel </v-btn>
                    <v-btn color="green darken-1" text @click="dialog = false"> Yes </v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
            </v-row>
            <br />
          </v-card-actions>
        </v-card>
      </v-row>
    </form>
  </v-container>
</template>

<script>
export default {
  name: 'AddLocker',
  data: () => ({
    dialog: false,
  }),
}
</script>
