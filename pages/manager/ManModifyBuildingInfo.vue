<template>
  <v-container>
    <v-row>
      <v-col>
        <v-card>
          <v-card-title class="text-h5 font-weight-regular pink darken-1 white--text">
            Modify Building
          </v-card-title>
          <v-card-text>
            <v-subheader class="pa-0"> Enter building number: </v-subheader>
            <v-autocomplete
              v-model="model"
              :hint="!isEditing ? 'Click the icon to edit' : 'Click the icon to save'"
              :items="states"
              :readonly="!isEditing"
              :label="`State — ${isEditing ? 'Editable' : 'Readonly'}`"
              persistent-hint
              prepend-icon="mdi-city">
              <template #append-outer>
                <v-slide-x-reverse-transition mode="out-in">
                  <v-icon
                    :key="`icon-${isEditing}`"
                    :color="isEditing ? 'success' : 'info'"
                    @click="isEditing = !isEditing"
                    v-text="isEditing ? 'mdi-check-outline' : 'mdi-circle-edit-outline'"></v-icon>
                </v-slide-x-reverse-transition>
              </template>
            </v-autocomplete>
          </v-card-text>
          <v-card-actions>
            <v-btn rounded color="error" @click="del"> Delete </v-btn>
            <v-btn rounded color="#FDBFA8" class="mr-4" @click="goToAddBuilding()">
              Add Building
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <form action="">
          <v-textarea
            clearable
            clear-icon="mdi-close-circle"
            label="building information:"
            value="change Building information here..."></v-textarea>
          <v-btn rounded class="mr-4" @click="submit"> submit </v-btn>
        </form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      isEditing: false,
      model: null,
      states: ['build1', 'build2', 'build3', 'build4'],
    }
  },
  methods: {
    goToAddBuilding() {
      this.$router.push('/manager/AddBuilding')
    },
    submit() {
      this.$refs.observer.validate()
    },
    del() {
      this.loading = true
      setTimeout(() => (this.loading = false), 2000)
    },
  },
}
</script>