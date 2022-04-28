<template>
  <v-container>
    <v-form ref="form" v-model="valid" lazy-validation>
      <v-text-field v-model="name" :counter="10" :rules="nameRules" label="Name" required></v-text-field>
      <v-text-field v-model="email" :rules="emailRules" label="E-mail" required></v-text-field>
      <v-textarea clearable clear-icon="mdi-close-circle" label="Message:" value=""></v-textarea>
      <v-btn rounded :disabled="!valid" type="submit" class="mr-4" @click="validate">
        submit
      </v-btn>
      <v-btn rounded color="error" class="mr-4" @click="reset"> Reset Form </v-btn>
      <v-btn rounded color="warning" @click="resetValidation"> Reset Validation </v-btn>
    </v-form>
    <img src="/vectortwo.png"  width="80%" />
  </v-container>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    name: '',
    nameRules: [
      (v) => !!v || 'Name is required',
      (v) => (v && v.length <= 10) || 'Name must be less than 10 characters',
    ],
    email: '',
    emailRules: [
      (v) => !!v || 'E-mail is required',
      (v) => /.+@.+\..+/.test(v) || 'E-mail must be valid',
    ],
    select: null,
  }),

  methods: {
    validate() {
      this.$refs.form.validate()
    },
    reset() {
      this.$refs.form.reset()
    },
    resetValidation() {
      this.$refs.form.resetValidation()
    },
  },
}
</script>
