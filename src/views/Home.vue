<template>
  <!-- <v-container>
    <stack ref="cpt" :column-min-width="200" :gutter-width="10" :gutter-height="10" monitor-images-loaded>
      <stack-item v-for="(item, i) in items" :key="i" style="transition: transform 300ms">
        <ImageCard :item="item" />
      </stack-item>
    </stack>
  </v-container> -->
  <v-container>
    <div v-masonry transition-duration="0.3s" item-selector=".item" class="masonry-container">
      <div v-masonry-tile class="item" v-for="(item, index) in items" :key="index">
        <ImageCard :item="item" />
      </div>
    </div>
  </v-container>
</template>

<script>
// import { Stack, StackItem } from 'vue-stack-grid'

import ImageCard from '@/components/ImageCard'

export default {
  name: 'Home',
  components: { ImageCard },
  data() {
    return {
      items: [
        {
          id: 1,
          name: 'Danny Weiss',
          followers: '304',
          avatar:
            'https://images.unsplash.com/photo-1552374196-c4e7ffc6e126?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80',
          photo:
            'https://images.unsplash.com/photo-1526392060635-9d6019884377?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80'
        },
        {
          id: 2,
          name: 'Jurica Koletić',
          followers: '684',
          avatar:
            'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80',
          photo:
            'https://images.unsplash.com/photo-1568805647702-3d8b49681088?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=2134&q=80'
        },
        {
          id: 3,
          name: 'Houcine Ncib',
          followers: '1,250',
          avatar:
            'https://images.unsplash.com/photo-1554151228-14d9def656e4?ixlib=rb-1.2.1&ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&auto=format&fit=crop&w=633&q=80',
          photo:
            'https://images.unsplash.com/photo-1532996228489-082708ddbde0?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=802&q=80'
        },
        {
          id: 4,
          name: 'Christopher Campbell',
          followers: '9,845',
          avatar:
            'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
          photo:
            'https://images.unsplash.com/photo-1531968455001-5c5272a41129?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1381&q=80'
        },
        {
          id: 5,
          name: 'Imansyah Muhamad Putera',
          followers: '15,475',
          avatar:
            'https://images.unsplash.com/photo-1542909168-82c3e7fdca5c?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80',
          photo:
            'https://images.unsplash.com/photo-1545206085-d0e519bdcecd?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1351&q=80'
        },
        {
          id: 6,
          name: 'Robert Godwin',
          followers: '65,475',
          avatar:
            'https://images.unsplash.com/photo-1504257432389-52343af06ae3?ixlib=rb-1.2.1&ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&auto=format&fit=crop&w=634&q=80',
          photo:
            'https://images.unsplash.com/photo-1546458544-801cbd163951?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1351&q=80'
        },
        {
          id: 7,
          name: 'Michael Dam',
          followers: '22,457',
          avatar:
            'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80',
          photo:
            'https://images.unsplash.com/photo-1526697675318-89790adec369?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=675&q=80'
        },
        {
          id: 8,
          name: 'Ludvig Wiese',
          followers: '153,778',
          avatar:
            'https://images.unsplash.com/photo-1509460913899-515f1df34fea?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80',
          photo:
            'https://images.unsplash.com/photo-1536594841504-5cf5155a4900?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80'
        },
        {
          id: 9,
          name: 'Prince Akachi',
          followers: '355,126',
          avatar:
            'https://images.unsplash.com/photo-1531123897727-8f129e1688ce?ixlib=rb-1.2.1&ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&auto=format&fit=crop&w=634&q=80',
          photo:
            'https://images.unsplash.com/photo-1473455811944-fdd1b0f282f3?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80'
        },
        {
          id: 10,
          name: 'Štefan Štefančík',
          followers: '5,825',
          avatar:
            'https://images.unsplash.com/photo-1544005313-94ddf0286df2?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80',
          photo:
            'https://images.unsplash.com/photo-1415804941191-bc0c3bbac10d?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80'
        }
      ]
    }
  },
  mounted: function() {
    this.$redrawVueMasonry()
  },
  methods: {
    reDraw: function() {
      this.$redrawVueMasonry()
    }
  }
}
</script>
<style>
.item {
  width: 230px;
}
.masonry-container {
  margin: 0 auto;
}
</style>
