<template>
  <v-card flat class="ma-1">
    <v-img :src="item.photo" style="border-radius:20px" />
    <v-layout align-center pa-3>
      <v-avatar size="40">
        <v-img :src="item.avatar" />
      </v-avatar>
      <v-flex class="ml-3">
        <div class="subtitle-2">{{ item.name }}</div>
        <div class="caption grey--text lighten-1">{{ item.followers }} followers</div>
      </v-flex>
    </v-layout>
  </v-card>
</template>
<script>
export default {
  props: ['item']
}
</script>
