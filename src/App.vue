<template>
  <v-app>
    <v-navigation-drawer permanent app>
      <Nav :items="items" :items2="items2" />
      <Banner />
    </v-navigation-drawer>

    <v-app-bar app color="white" flat height="100">
      <v-layout row wrap align-center class="mx-0">
        <v-text-field
          v-model="keyword"
          solo-inverted
          flat
          filled
          label="Search..."
          prepend-inner-icon="mdi-magnify"
          hide-details
          class="mr-5"
          style="border-radius:10px"
          @keyup.enter="search"
        ></v-text-field>
        <v-btn style="border-radius:10px" height="56" depressed class="mr-5"><v-icon>mdi-tune-vertical-variant</v-icon></v-btn>
        <v-btn style="border-radius:10px" height="56" depressed dark><v-icon>mdi-plus</v-icon></v-btn>
      </v-layout>
    </v-app-bar>
    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
import Nav from '@/components/Nav'
import Banner from '@/components/Banner'

export default {
  name: 'App',
  components: { Nav, Banner },
  data() {
    return {
      keyword: '',
      items: [
        { title: 'Home', icon: 'mdi-home', to: '/' },
        { title: 'Recent', icon: 'mdi-clock-time-three' },
        { title: 'Following', icon: 'mdi-account-multiple' }
      ],
      items2: [
        { title: 'Message', icon: 'mdi-message-reply-text', count: '' },
        { title: 'Notifications', icon: 'mdi-bell', count: '2' }
      ]
    }
  },
  methods: {
    search() {
      this.$eventBus.$emit('search', this.keyword)
      this.keyword = ''
    }
  }
}
</script>
<style lang="scss">
img {
  width: 100%;
}
</style>
