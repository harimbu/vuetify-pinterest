<template>
  <v-container>
    <stack :column-min-width="240" :gutter-width="10" :gutter-height="10" monitor-images-loaded>
      <stack-item v-for="(item, i) in images" :key="i" style="transition: transform 300ms">
        <ImageCard :item="item" />
      </stack-item>
    </stack>
  </v-container>
</template>

<script>
import { Stack, StackItem } from 'vue-stack-grid'
import ImageCard from '@/components/ImageCard'
import axios from 'axios'

export default {
  name: 'Home',
  components: { ImageCard, Stack, StackItem },
  data() {
    return {
      keyword: 'cat',
      images: []
    }
  },

  created() {
    this.$eventBus.$on('search', payload => {
      this.keyword = payload
      this.getImage(this.keyword)
    })
    this.getImage(this.keyword)
  },
  methods: {
    getImage(topic) {
      this.images = []
      axios
        .get(`https://api.unsplash.com/search/photos?query=${topic}&per_page=20`, {
          headers: {
            Authorization: `Client-ID e6MD8Gpf5agAWPP4BsapuMe7Htj7sOSXMluIMTbuAXo`
          }
        })
        .then(response => {
          this.images = response.data.results
        })
        .catch(() => {
          this.images = []
        })
    }
  }
}
</script>
