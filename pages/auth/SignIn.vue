<template>
  <v-layout align-center>
    <img src="/Locker.png" alt="Locker" height="600" width="500" />
    <v-flex xs12 sm8 md4>
      <h2>Welcome to LMRS</h2>
      <overline class="font-weight-light"> Locker Managemenr & Reservation System </overline>
      <v-card-text>
        <v-form>
          <v-text-field
            prepend-icon="person"
            name="ID"
            label="Enter your ID"
            type="text"
            color="#D43256">
          </v-text-field>
          <v-text-field
            id="password"
            prepend-icon="lock"
            name="password"
            label="Password"
            type="password"
            color="#D43256">
          </v-text-field>
        </v-form>
        <v-row>
          <v-col>
            <v-btn text color="#D43256" to="/Auth/SignUp">Create account</v-btn>
          </v-col>
        </v-row>
        <v-btn text color="#D43256" to="/Auth/ResetPassword">Forget Password?</v-btn>
      </v-card-text>
      <v-card-actions>
        <v-btn block rounded color="#FDBFA8" to="/">Log in </v-btn>
      </v-card-actions>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  name: 'SignIn',
  props: {
    // eslint-disable-next-line vue/require-default-prop
    source: String,
  },
}
</script>

<style>
#app {
  background-color: #fdfaf6;
}

h2,
overline {
  padding: 2rem;
}
</style>
