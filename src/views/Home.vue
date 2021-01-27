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
    getImage(query) {
      this.$unsplash.search
        .getPhotos({ query: query, orientation: 'portrait', page: 1, perPage: 20 })
        .then(result => {
          this.images = result.response.results
        })
        .catch(e => {
          console.log(e.message)
        })
    }
    // getImage(topic) {
    //   this.images = []
    //   axios
    //     .get(`https://api.unsplash.com/search/photos?query=${topic}&per_page=20`, {
    //       headers: {
    //         Authorization: `Client-ID app-key`
    //       }
    //     })
    //     .then(response => {
    //       this.images = response.data.results
    //     })
    //     .catch(() => {
    //       this.images = []
    //     })
    // }
  }
}
</script>
