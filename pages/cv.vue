<script>

export default {
  name: 'IndexPage',
  head(){
    return {
      titleTemplate: '%s - CV'
    }
  },
  data(){
    return {
      pdfHeight: 500
    }
  },
  mounted(){
    this.pdfHeight = window.innerHeight * 0.8
  }
}
</script>

<template>
  <v-container >
    <v-row>
      <v-col cols="12">
        <iframe src="https://alex-bailon.github.io/assets/images/CV.pdf" width="100%" :height="pdfHeight"/>
      </v-col>
    </v-row>    
  </v-container>
</template>
