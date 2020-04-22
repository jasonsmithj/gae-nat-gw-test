<template>
  <v-layout align-center justify-center>
    <v-flex xs24 md24 text-xs-center>
      <v-card flat >
        <v-card-title class="justify-center">
          <h2>Gateway IP: {{ origin }}</h2>
        </v-card-title>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script lang="ts">
  import { Component, Vue } from 'vue-property-decorator'
  import axios from 'axios'

  @Component({
    async asyncData() {
      const res = await axios.get("https://httpbin.org/ip")
      return res.data
    }
  })
  export default class GetGatewayIP extends Vue {
  }
</script>
