<template>
  <v-app dark>
    <Nav />
    <Nuxt />
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  head() {
      return {
      link: [
          { rel: "preconnect", href:"https://fonts.googleapis.com" },
          { rel: "preconnect", href: "https://fonts.gstatic.com", crossorigin: true},
          { href: "https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap", rel: "stylesheet"},
          { href: "https://fonts.googleapis.com/icon?family=Material+Icons", rel: "stylesheet" }
      ]
      }
  },
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>
