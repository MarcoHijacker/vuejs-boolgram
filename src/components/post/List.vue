<template>

  <div class="postsList">
    <Post v-for="(p,i) in posts" :key="`p${i}`" :data="p" />
  </div>

</template>

<script>

import axios from 'axios';
import Post from './Item'
export default {
  name: 'PostsList',
  components: {
    Post,
  },
  data: () => ({
    posts: [],
    showAll: false
  }),
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/boolgram/posts')
      .then(({data}) => this.posts = data)
      .finally(() => console.log('Posts Data loading completed.'));
  },
}

</script>
