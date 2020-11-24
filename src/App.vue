<template>
  <v-app>
    <v-app-bar app height="30" color="#808080">
      <v-spacer></v-spacer>
      <span style="color: white">Call Us Now: +62 812-1133-5608</span>
      <span class="subtitle-1 pl-6" style="color: white">English</span>
      <v-menu
        bottom
        offset-y
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            v-bind="attrs"
            v-on="on"
            icon
          >
            <v-icon color="white">mdi-chevron-down</v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item>
            <v-list-item-title>Indonesia</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>

    <v-content>
      <v-container class="fill-height" fluid>
        <v-row align="center" justify="center">
          <v-col cols="12" sm="8" md="8">
            <v-card width="500" height="600" class="mx-auto mt-9">
              <v-row justify="center">
                <v-col cols="12" sm="6" md="6" style="padding-top: 50px">
                  <v-img src="https://via.placeholder.com/250x100" width="250" height="100"></v-img>
                </v-col>
              </v-row>
              <v-row justify="center">
                <v-col cols="12" sm="6" md="8" class="text-center">
                  Your one stop platform to manage all of your field service management
                </v-col>
              </v-row>
              <v-row justify="center">
                <v-col cols="12" sm="6" md="8" class="pb-0">
                  <v-text-field v-model="organizationName" label="Enter your organization's name" solo></v-text-field>
                </v-col>
              </v-row>
              <v-row v-if="error" justify="center">
                <v-col cols="12" sm="6" md="8" class="pb-0 pt-0">
                  <span class="red--text">The organization name field cannot empty</span>
                </v-col>
              </v-row>
              <v-row justify="center">
                <v-col cols="12" sm="6" md="8" class="pt-0">
                  <v-btn @click="submit()" block color="blue">
                    <span style="color: white">Login</span>
                  </v-btn>
                </v-col>
              </v-row>
              <v-row justify="center">
                <v-col cols="12" sm="6" md="8" class="text-center">
                  Not registered yet? <a href="#" style="text-decoration: none">Register here</a>
                </v-col>
              </v-row>
              <v-row justify="left">
                <v-col cols="12" sm="6" md="8" class="text-center">
                  <a href="#" style="text-decoration: none">
                    <v-icon small>mdi-arrow-left</v-icon>
                    Back to Mile</a>
                </v-col>
              </v-row>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-content>

    <template>
  <v-footer>
  </v-footer>
</template>
  </v-app>
</template>
<script>
export default {
  data() {
    return{
      showPassword:false,
      organizationName: '',
      error: false,
    }
  },
  methods: {
    submit: function() {
      if (this.organizationName === '') this.error = true;
      else console.log(this.organizationName);
    }
  },
  computed: {
    validator: function () {
      return this.organizationName.length > 0
    }
  }
}
</script>