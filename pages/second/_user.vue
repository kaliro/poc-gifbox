<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
            <v-card>
        <v-card-title class="headline">
          Hola, @{{currentUser.user}} tienes un segundo detalle.
        </v-card-title>
        <v-card-text>
          <p>{{currentUser.text}}</p>
          <div class="text-xs-right">
            <em><small>con cariño <br> &mdash;  {{currentUser.from}}</small></em>
          </div>
          <hr class="my-3">
          <br>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>


<script>
import rawData from 'assets/data.json'

export default {
  data() {
    return {
      currentUserName: this.$route.params.user
      // allStory: rawStory.Stories,
      // slideTime: rawStory.TimeSlider,
      // showSpot: rawStory.ShowSpot,
    }
  },
  computed: {
    currentUser() {
      return rawData.find(x=> x.user===this.$route.params.user)
    },
  }
}
</script>
