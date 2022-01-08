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
      <v-app-bar-nav-icon v-else @click="navDrawer = true"/>
    </v-app-bar>
    <v-navigation-drawer v-model="navDrawer" absolute temporary>
      <v-list-item to="/">
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
      <v-container >
        <Nuxt />
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
      navDrawer: false
    }
  }
}
</script>
