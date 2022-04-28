<template>
    <v-container fluid fill-height>
      <v-layout>
        <v-flex xs12 sm12 md6>
          <v-card class="elevation-12">
            <v-toolbar color="#FDBFA8">
              <v-toolbar-title>Reset Password</v-toolbar-title>
            </v-toolbar>
            <v-card-text>
              <v-form>
                <v-text-field prepend-icon="email" name="email" label="Email" type="email">
                </v-text-field>
                <v-text-field
                  prepend-icon="lock"
                  name="password"
                  label="Old password"
                  type="password">
                </v-text-field>
                <v-text-field prepend-icon="lock" name="password" label="Password" type="password">
                </v-text-field>
                <v-text-field
                  prepend-icon="lock"
                  name="repassword"
                  label="Confirm Password"
                  type="password">
                </v-text-field>
              </v-form>
            </v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn rounded color="#D43256" to="/">Reset</v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
</template>

<script>
export default {
  name: 'ResetPassword',
  props: {
    // eslint-disable-next-line vue/require-default-prop
    source: String,
  },
}
</script>

<style></style>
