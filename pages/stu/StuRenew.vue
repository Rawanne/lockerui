<template>
  <v-container>
    <v-row>
      <v-card class="mx-auto" max-width="820" elevation="2">
        <v-card-title>
          <h2 class="text-h4">Your information:</h2>
          <v-spacer></v-spacer>
        </v-card-title>
        <v-card-text>
          <v-chip-group active-class="deep-purple--text text--accent-4">
            <v-chip>Building Number: 150</v-chip>
            <v-chip>Number of lockers: 2</v-chip>
            <v-chip>Subscription term: 2</v-chip>
          </v-chip-group>
        </v-card-text>
        <v-divider class="mx-4"></v-divider>
        <form action="">
          <v-card-text>
            <v-select :items="cterm" label="Choose subscription term"></v-select>
          </v-card-text>
          <v-card-actions>
            <v-row justify="center">
              <v-col>
                <v-dialog v-model="dialog" persistent max-width="450">
                  <template #activator="{on, attrs}">
                    <v-btn color="#D43256" rounded dark v-bind="attrs" v-on="on">confirm</v-btn>
                  </template>
                  <v-card>
                    <v-card-title class="text-h5">
                      Are you sure about this information?
                    </v-card-title>
                    <v-card-text> are you sure you want to renew your reservation. </v-card-text>
                    <v-card-actions>
                      <v-spacer></v-spacer>
                      <v-btn color="red darken-1" text @click="dialog = false"> Cancel </v-btn>
                      <v-btn color="green darken-1" text @click="dialog = false"> Yes </v-btn>
                    </v-card-actions>
                  </v-card>
                </v-dialog>
              </v-col>
            </v-row>
            <br />
          </v-card-actions>
        </form>
      </v-card>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'StuRenew',
  data: () => ({
    cterm: ['Term 1', 'Term 2'],
    dialog: false,
  }),
}
</script>
