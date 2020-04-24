<template>
  <v-container>
    <!-- input field -->
    <v-form @submit.prevent="getAvatarIg()">
      <v-container>
        <v-layout row wrap class="d-flex justify-center">
          <v-flex xs12 sm6 md3>
            <v-text-field label="Outline" outline v-model="username"></v-text-field>
          </v-flex>
        </v-layout>
      </v-container>
    </v-form>
    <!-- cards -->
    <v-layout class="d-flex justify-center mt-10">
      <v-flex xs12 sm6 lg2 md4>
        <v-card>
          <v-img class="white--text" height="320px" width="320px" :src="avatar">
            <!-- <v-container fill-height fluid> -->
            <!-- <v-layout fill-height>
                <v-flex xs12 align-end flexbox>
                  <span class="headline">{{platform}}</span>
                </v-flex>
            </v-layout>-->
            <!-- </v-container> -->
          </v-img>
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

      platform: "",
      username: "",
      myurl: "",
      status: ""
    };
  },
  methods: {
    async getAvatarIg() {
      let apiUrl = "https://unavatar.now.sh/instagram/";
      apiUrl = apiUrl + this.username + "?json";
      await fetch(apiUrl).then(response => (this.status = response.status));
      console.log(this.status);
      if (this.status == 200) {
        this.avatar = "https://unavatar.now.sh/instagram/" + this.username;
      }
    }
  }
};
</script>
