<script>
import bio from '@/static/bio'
export default {
  name: 'Bio',
  methods: {
    buildSite(){
      this.$axios.post('https://api.netlify.com/build_hooks/636578834863db03ec1829ee')
    }
  }
}
</script>

<template>
  <v-row justify="center" align="center">
    <v-col cols="12">
      <v-btn @click="buildSite" >Build</v-btn>
    </v-col>
  </v-row>
</template>

