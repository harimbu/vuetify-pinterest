<template>
  <div>
    <v-list-item>
      <v-list-item-avatar class="my-5">
        <v-img src="https://cdn0.iconfinder.com/data/icons/Pinterest/256/Pinterest_Favicon.png"></v-img>
      </v-list-item-avatar>
      <v-list-item-content>
        <v-list-item-title class="title">
          Pinterest
        </v-list-item-title>
      </v-list-item-content>
    </v-list-item>

    <v-list dense nav>
      <v-list-item v-for="item in items" :key="item.title" link>
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
      <v-list-item link>
        <v-list-item-icon>
          <v-icon>mdi-message-reply-text</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>Message</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-list-item link>
        <v-list-item-icon>
          <v-icon>mdi-bell</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>Notifications</v-list-item-title>
        </v-list-item-content>

        <v-list-item-avatar size="26" color="orange darken-2" class="white--text caption">2</v-list-item-avatar>
      </v-list-item>
    </v-list>
  </div>
</template>
<script>
export default {
  props: ['items']
}
</script>
