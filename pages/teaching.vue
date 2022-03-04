<script>
import teaching from '@/static/teaching'
export default {
  name: 'teachingPage',
  head(){
    return {
      titleTemplate: '%s - Teaching'
    }
  },  
  data(){
    return {
      teaching
    }
  }
}
</script>

<template>
  <div>
    <v-row justify="center" align="center">
      <v-col cols="12">
        <h3 v-html="teaching.intro" />
        <blockquote class="blockquote" v-html="teaching.quote" />
      </v-col>
    </v-row>
    <v-row v-for="course in teaching.courses" :key="course.title" class="py-5">
      <v-col class="py-0" cols="6" v-html="course.title" />
      <v-col class="py-0" cols="6" v-html="course.dates" style="text-align: right;" />
      <v-col class="py-0" cols="6" v-html="course.school" />
      <v-col class="py-0" cols="6" v-html="course.location" style="text-align: right;" />
      <v-col class="py-0 pl-10" cols="12" v-html="course.description" />                 
    </v-row>
  </div>
</template>
