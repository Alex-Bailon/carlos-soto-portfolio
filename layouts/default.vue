<template>
  <v-app>
    <v-app-bar
      fixed
      app
    >
      <v-toolbar-title v-text="title" @click="$router.push('/')" style="cursor: pointer" />
      <v-spacer />
      <div v-if="$vuetify.breakpoint.smAndUp">
        <v-btn v-for="link in links" :key="link.text" :to="link.to" text><v-icon left v-text="link.icon"/>{{ link.text }}</v-btn>
      </div>
      <v-app-bar-nav-icon v-else @click="setYOffset(), navDrawer = true"/>
    </v-app-bar>
    <v-navigation-drawer v-model="navDrawer" absolute temporary>
      <v-list-item to="/" :style="{paddingTop: `${yOffset}px`}" >
        <v-list-item-content>
          <v-list-item-title class="text-h6" v-text="title" />
        </v-list-item-content>
      </v-list-item>
      <v-divider />
      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="link in links"
          :key="link.text"
          :to="link.to"
        >
          <v-list-item-icon>
            <v-icon>{{ link.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ link.text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <v-container fluid >
        <v-row>
          <v-col cols="12" md="2">
            <v-img src="/profile_img.jpg" width="100%" min-height="200" />
            <p class="px-2">Contact information:</p>
            <p class="px-2">Name: Carlos J. Soto</p>
			<p class="px-2">Email Address: <a href="mailto:carlossoto@umass.edu">carlossoto@umass.edu</a></p>
			<p class="px-2">My Links:</p>            
            <p class="px-2"><a href="https://scholar.google.com/citations?user=KN5sEEkAAAAJ&hl=en" target="_blank">Google Scholar</a></p>
			<p class="px-2"><a href="https://dblp.org/pid/191/6617-2.html" target="_blank">DBLP</a></p>
			<p class="px-2"><a href="https://github.com/otosjc" target="_blank">GitHub</a></p>
            <p class="px-2">ORCID: 0000-0003-0645-5770</p>
          </v-col>
          <v-col cols="12" md="10">
            <Nuxt />
          </v-col>
        </v-row>
      </v-container>
    </v-main>
    <v-footer
      absolute
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      title: 'Carlos Soto',
      links: [
        {
          to: '/bio',
          text: 'Bio',
          icon: 'mdi-account-circle'
        },
        {
          to: '/research',
          text: 'Research',
          icon: 'mdi-note-search'
        },
        {
          to: '/teaching',
          text: 'Teaching',
          icon: 'mdi-human-male-board'
        },
        {
          to: '/cv',
          text: 'CV',
          icon: 'mdi-file-account'
        }
      ],
      navDrawer: false,
      yOffset: 0
    }
  },
  methods: {
    setYOffset(){
      this.yOffset = window.scrollY
    }
  }
}
</script>
