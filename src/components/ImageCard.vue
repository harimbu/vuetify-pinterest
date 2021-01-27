<template>
  <v-card flat class="ma-1">
    <img :src="item.urls.small" style="border-radius:20px" />
    <v-layout align-center pa-3>
      <v-avatar size="40">
        <v-img :src="item.user.profile_image.medium" />
      </v-avatar>
      <v-flex class="ml-3">
        <div class="subtitle-2" v-text="`${item.user.first_name} ${item.user.last_name}`"></div>
        <div class="caption grey--text lighten-1">{{ item.likes }} likes</div>
      </v-flex>
    </v-layout>
  </v-card>
</template>
<script>
export default {
  props: ['item']
}
</script>
