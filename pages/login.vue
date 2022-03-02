<template>
    <v-app>
      <v-content @submit="login">
        <v-card width="500" class="mx-auto mt-9">
          <v-card-title>Log in</v-card-title>
          <v-card-text>
            <v-text-field
              label="Username"
              prepend-icon="mdi-account-circle"
            ></v-text-field>
            <v-text-field
              label="Password"
              :type="showPassword ? 'text' : 'password'"
              prepend-icon="mdi-lock"
              :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
              @click:append="showPassword = !showPassword"
            >
            </v-text-field>
          </v-card-text>
          <v-divider></v-divider>
          <v-card-actions>
            <v-btn color="success">Login</v-btn>
          </v-card-actions>
        </v-card>
      </v-content>
    </v-app>
</template>
<script>
export default {
  data() {
    return {
      showPassword: false,
      username: '',
      password: '',
      user: 'admin',
      pass: 'admin',
    }
  },
  methods: {
    login() {
      if (this.username === this.user && this.password === this.pass) {
        window.location = 'index.vue'
      }
    },
  },
}
</script>
