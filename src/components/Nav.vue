<template>
  <div>
    <v-list-item>
      <v-list-item-avatar class="my-5">
        <v-img src="https://cdn0.iconfinder.com/data/icons/Pinterest/256/Pinterest_Favicon.png"></v-img>
      </v-list-item-avatar>
      <v-list-item-content>
        <v-list-item-title class="title"><span class="logo">Pinterest</span></v-list-item-title>
      </v-list-item-content>
    </v-list-item>

    <v-list dense nav>
      <v-list-item v-for="item in items" :key="item.title" :to="item.to">
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>

    <div class="subtitle-1 ml-4 pt-5 grey--text">Insights</div>

    <v-list dense nav>
      <v-list-item v-for="item in items2" :key="item.title">
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
        <v-list-item-avatar size="26" color="pink accent-2" class="white--text caption" v-if="item.count">{{ item.count }}</v-list-item-avatar>
      </v-list-item>
    </v-list>
  </div>
</template>
<script>
export default {
  props: ['items', 'items2']
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');

.logo {
  font-family: 'Pacifico', cursive;
  font-size: 26px;
}
</style>
