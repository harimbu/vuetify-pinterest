<template>
  <v-card flat class="ma-1">
    <v-img :src="item.urls.regular" style="border-radius:20px" />
    <v-layout align-center pa-3>
      <v-avatar size="40">
        <v-img :src="item.user.profile_image.large" />
      </v-avatar>
      <v-flex class="ml-3">
        <div class="subtitle-2">{{ item.user.name }}</div>
        <div class="caption grey--text lighten-1">{{ item.user.location === null ? 'Earth' : `${item.user.location}` }}</div>
      </v-flex>
    </v-layout>
  </v-card>
</template>
<script>
export default {
  props: ['item']
}
</script>
