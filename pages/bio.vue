<script>
import bio from '@/static/bio'
export default {
  name: 'Bio',
  data(){
    return {
      bio,
    }
  }
}
</script>

<template>
  <v-row justify="center" align="center">
    <v-col cols="12">
      <h3 v-html="bio"></h3>
    </v-col>
  </v-row>
</template>

