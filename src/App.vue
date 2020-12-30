<template>

  <div id="app">
    <HeaderArea/>
    <div class="fullBlock">
      <div class="leftBlock">
        <SuggStories/>
        <PostsList/>
      </div>
      <div class="rightBlock">
        <SuggProfiles/>
      </div>
    </div>
  </div>

</template>

<script>

import SuggProfiles from './components/SuggProfiles.vue'
import SuggStories from './components/SuggStories.vue'
import HeaderArea from './components/HeaderArea.vue'
import PostsList from './components/post/List.vue'

export default {
  name: 'App',
  components: {
    SuggProfiles,
    SuggStories,
    HeaderArea,
    PostsList
  }
}

</script>

<style lang="scss">

@import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap');

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
body {
  background-color: #fafafa;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.fullBlock {
  display: flex;
  justify-content: space-between;
  padding-top: 50px;
}
.leftBlock {
  padding-left: 200px;
}
.rightBlock {
  padding-right: 200px;
}

</style>
