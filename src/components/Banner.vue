<template lang="">
  <div>
    <v-card flat>
      <v-img white="80%" :src="bgSrc"></v-img>
    </v-card>
    <v-layout class="pt-2 px-5">
      <v-flex text-center>
        <div class="subtitle-2 blue--text">Unlock Business Tools</div>
        <div class="caption">Hurry Up! Now you can unlock out new business tools at your Convenience.</div>
      </v-flex>
    </v-layout>

    <v-card class="my-7 mx-4" style="border-radius:16px" elevation="3">
      <v-list>
        <v-list-item link>
          <v-list-item-avatar size="36">
            <v-img :src="avatar"></v-img>
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title class="subtitle-2">{{ name }}</v-list-item-title>
            <v-list-item-subtitle class="caption">{{ login }}</v-list-item-subtitle>
          </v-list-item-content>
          <v-list-item-action>
            <v-icon>mdi-chevron-right</v-icon>
          </v-list-item-action>
        </v-list-item>
      </v-list>
    </v-card>
  </div>
</template>
<script>
export default {
  data() {
    return {
      bgSrc: 'https://assets.website-files.com/5bff8886c3964a992e90d465/5bff98f85ea7faf86504605e_scenes.gif',
      avatar:
        'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
      name: 'Chris Campbe',
      login: '10/08/20'
    }
  }
}
</script>
