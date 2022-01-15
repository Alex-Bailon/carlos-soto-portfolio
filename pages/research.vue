<script>
import research from '@/static/research'
export default {
  name: 'Research',
  data(){
    return {
      intro: research.intro,
      papers: research.papers,
      dialog: false,
      dialogText: ''
    }
  }
}
</script>

<template>
  <v-row justify="center" align="center">
    <v-col cols="12">
      <h3 v-html="intro"></h3>
      <ul>
        <li v-for="paper in papers" :key="paper.title" >
          <a :href="paper.link" target="_blank" v-html="paper.title"></a> --
          <p @click="dialogText = paper.bibText, dialog = true" class="bibtextBtn">BibText</p>
        </li>
      </ul>
    </v-col>
    <v-dialog
      v-model="dialog"
      max-width="500px"
      transition="dialog-transition"
    >
      <v-card>
        <v-card-title primary-title>
          BibText
        </v-card-title>
        <v-card-text v-html="dialogText">
        </v-card-text>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<style scoped lang="scss">
  .bibtextBtn {
    cursor: pointer;
    color: red ;
    display: inline-block;
  }
</style>