<template>
  <v-container>
    <form>
      <v-select v-model="name" :items="cbuilding" label="Choose number of Building"></v-select>
      <v-select v-model="name2" :items="clocker" label="Choose number of Locker"></v-select>
      <v-textarea
        name="input-7-1"
        label="problem you want to fix"
        value="list it here..."
        hint="Hint text"></v-textarea>
      <v-checkbox
        v-model="checkbox"
        :error-messages="checkboxErrors"
        label="Do you agree?"
        required
        @change="$v.checkbox.$touch()"
        @blur="$v.checkbox.$touch()"></v-checkbox>
      <v-btn rounded class="mr-4" @click="submit"> submit </v-btn>
      <v-btn rounded color="warning" @click="clear"> clear </v-btn>
    </form>
  </v-container>
</template>
<script>
import {validationMixin} from 'vuelidate'
import {required, maxLength} from 'vuelidate/lib/validators'

export default {
  mixins: [validationMixin],

  validations: {
    name: {required, maxLength: maxLength(10)},
    select: {required},
    checkbox: {
      checked(val) {
        return val
      },
    },
  },

  data: () => ({
    cbuilding: ['Building 1', 'Building 2', 'Building 3', 'Building 4'],
    clocker: ['Locker 1', 'Locker 2', 'Locker 3'],
    name: '',
    name2: '',
    select: null,
    checkbox: false,
  }),

  computed: {
    checkboxErrors() {
      const errors = []
      if (!this.$v.checkbox.$dirty) return errors
      !this.$v.checkbox.checked && errors.push('You must agree to continue!')
      return errors
    },
    selectErrors() {
      const errors = []
      if (!this.$v.select.$dirty) return errors
      !this.$v.select.required && errors.push('Item is required')
      return errors
    },
    nameErrors() {
      const errors = []
      if (!this.$v.name.$dirty) return errors
      !this.$v.name.maxLength && errors.push('Name must be at most 10 characters long')
      !this.$v.name.required && errors.push('Name is required.')
      return errors
    },
  },

  methods: {
    submit() {
      this.$v.$touch()
    },
    clear() {
      this.$v.$reset()
      this.name = ''
      this.name2 = ''
      this.select = null
      this.checkbox = false
    },
  },
}
</script>