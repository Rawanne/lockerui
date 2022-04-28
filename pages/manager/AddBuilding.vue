<template>
  <v-container fluid>
    <form action="">
      <v-row align="center">
        <v-col class="d-flex" cols="12" sm="4">
          <v-text-field label="Enter Building number" placeholder="1"></v-text-field>
        </v-col>
      </v-row>
      <v-row align="center">
        <v-col class="d-flex" cols="12" sm="4">
          <v-text-field label="Enter Building name" placeholder="building 1"></v-text-field>
        </v-col>
      </v-row>
      <v-row align="center">
        <v-col class="d-flex" cols="12" sm="4">
          <v-text-field label="Number of lockers" placeholder="10"></v-text-field>
        </v-col>
      </v-row>
    </form>
    <v-row justify="center">
      <v-dialog v-model="dialog" persistent max-width="450">
        <template #activator="{on, attrs}">
          <v-btn color="#D43256" rounded dark v-bind="attrs" v-on="on">confirm</v-btn>
        </template>
        <v-card>
          <v-card-title class="text-h5"> Are you sure about this information? </v-card-title>
          <v-card-text>
            you will add new Building if you clicked Yes.
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="red darken-1" text @click="dialog = false"> Cancel </v-btn>
            <v-btn color="green darken-1" text @click="dialog = false"> Yes </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'AddBuilding',
  data: () => ({
    dialog: false,
  }),
}
</script>
