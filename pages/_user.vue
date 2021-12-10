<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
            <v-card>
        <v-card-title class="headline">
          {{currentUser.name}}
        </v-card-title>
        <v-card-text>
          <p>{{currentUser.message}}</p>
          <p>{{currentUser.message2}}</p>
          <div class="text-xs-right">
            <em><small>&mdash; {{currentUser.from}}</small></em>
          </div>
          <hr class="my-3">
          <br>
        </v-card-text>
        <v-card-actions v-if="currentUser.text.length > 0">
          <v-spacer />
          <v-btn
            color="primary"
            nuxt
            :to="theLinkTo"
          >
            Reclamar
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>


<script>
import rawData from 'assets/data.json'

export default {
  data() {
    return {
      currentUserName: this.$route.params.user,
      theLinkTo: '/second/'+ this.$route.params.user
    }
  },
  computed: {
    currentUser() {
      return rawData.find(x=> x.user===this.currentUserName)
    },
  }
}
</script>
