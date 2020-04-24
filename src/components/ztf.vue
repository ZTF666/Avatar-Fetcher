<template>
  <v-container class="mt-10">
    <!-- snackbar -->
    <v-snackbar
      v-model="snackbar"
      :bottom="y === 'bottom'"
      :left="x === 'left'"
      :multi-line="mode === 'multi-line'"
      :right="x === 'right'"
      :timeout="timeout"
      :top="y === 'top'"
      :vertical="mode === 'vertical'"
    >
      {{ errormsg }}
      <v-btn color="pink" @click="snackbar = false">Close</v-btn>
    </v-snackbar>
    <!--  -->

    <!--  -->
    <!-- input field -->
    <v-form @submit.prevent="getAvatarIg()">
      <v-container>
        <v-layout row wrap class="d-flex justify-center">
          <v-flex xs12 sm6 md3>
            <v-text-field
              label="Outline"
              outline
              v-model="username"
            ></v-text-field>
          </v-flex>
          <!-- radio -->
          <v-container fluid class="d-flex justify-center">
            <v-radio-group v-model="row" row>
              <v-radio label="Facebook" value="fb" color="primary"></v-radio>
              <v-radio label="Instagram" value="ig" color="pink"></v-radio>
              <v-radio label="Twitter" value="tw" color="info"></v-radio>
            </v-radio-group>
          </v-container>
          <!-- end radio -->
        </v-layout>
      </v-container>
    </v-form>
    <!-- cards -->
    <v-layout class="d-flex justify-center mt-10">
      <v-flex class="d-flex justify-center mt-10">
        <v-card>
          <v-img
            class="white--text"
            height="320px"
            width="320px"
            :src="avatar"
          ></v-img>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: "ztf",

  data() {
    return {
      avatar: "",
      downloadlink: "",
      platform: "",
      username: null,
      myurl: "",
      status: "",
      row: null,
      alert: false,
      errormsg: "",
      // snackbar vars
      snackbar: false,
      y: "top",
      x: null,
      mode: "",
      timeout: 6000,
    };
  },
  methods: {
    async getAvatarIg() {
      if (this.username != null && this.row != null) {
        if (this.row == "ig") {
          let apiUrl = "https://unavatar.now.sh/instagram/";
          apiUrl = apiUrl + this.username + "?json";
          await fetch(apiUrl).then(
            (response) => (this.status = response.status)
          );
          console.log(this.status);
          if (this.status == 200) {
            this.avatar = "https://unavatar.now.sh/instagram/" + this.username;
            this.downloadlink =
              "https://unavatar.now.sh/instagram/" + this.username;
            this.username = null;
          }
        } else if (this.row == "fb") {
          let apiUrl = "https://unavatar.now.sh/facebook/";
          apiUrl = apiUrl + this.username + "?json";
          await fetch(apiUrl).then(
            (response) => (this.status = response.status)
          );
          console.log(this.status);
          if (this.status == 200) {
            this.avatar = "https://unavatar.now.sh/facebook/" + this.username;
            this.downloadlink =
              "https://unavatar.now.sh/facebook/" + this.username;
            this.username = null;
          }
        } else {
          let apiUrl = "https://unavatar.now.sh/twitter/";
          apiUrl = apiUrl + this.username + "?json";
          await fetch(apiUrl).then(
            (response) => (this.status = response.status)
          );
          console.log(this.status);
          if (this.status == 200) {
            this.avatar = "https://unavatar.now.sh/twitter/" + this.username;
            this.downloadlink =
              "https://unavatar.now.sh/twitter/" + this.username;
            this.username = null;
          }
        }
      } else if (this.username == null && this.row != null) {
        // this.alert = true;
        this.snackbar = true;
        this.errormsg = "Please type in a username ! Thank you .";
      } else if (this.username != null && this.row == null) {
        // this.alert = true;
        this.snackbar = true;
        this.errormsg = "Please select a platform ! Thank you .";
      } else {
        // this.alert = true;
        this.snackbar = true;
        this.errormsg =
          "Please type in a username and select a platform ! Thank you .";
      }
    },
    close() {
      this.alert = false;
    },
  },
};
</script>
