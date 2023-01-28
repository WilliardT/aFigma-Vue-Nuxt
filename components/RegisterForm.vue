<template>
  <div class="form-section d-flex justify-content-center align-center">
    <v-col>
      <h2>Try Figma for free</h2>
      <v-form v-model="valid">
        <v-text-field
          v-model="email"
          :rules="emailRules"
          label="e-mail"
          required
        >
        </v-text-field>
        <v-text-field
          v-model="password"
          :rules="passwordRules"
          label="Password"
          required
        >
        </v-text-field>
        <v-btn depressed color="blue"> Create acc </v-btn>
      </v-form>
    </v-col>
  </div>
</template>

<script>
export default {
  data: () => ({
    valid: false,
    firstname: '',
    lastname: '',
    nameRules: [
      (v) => !!v || 'name is required',
      (v) => v.length <= 10 || 'name must be less than 10 characters',
    ],
    email: '',
    emailRules: [
      (v) => !!v || 'E-mail is required',
      (v) => /.+@.+/.test(v) <= 10 || 'E-mail must be valid',
    ],
    password: '',
    passwordRules: [
      (v) => !!v || 'Password is required',
      (v) => v.length > 6 || 'Password must be valid',
    ],
  }),
}
</script>

<style scoped>
.form-section {
  height: 95vh;
}
</style>
