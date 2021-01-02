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
    <FooterArea/>
  </div>

</template>

<script>

import SuggProfiles from './components/SuggProfiles.vue'
import SuggStories from './components/SuggStories.vue'
import HeaderArea from './components/HeaderArea.vue'
import PostsList from './components/post/List.vue'
import FooterArea from './components/FooterArea.vue'

export default {
  name: 'App',
  components: {
    SuggProfiles,
    SuggStories,
    HeaderArea,
    PostsList,
    FooterArea
  }
}

</script>

<style lang="scss">

@import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap');

@media only screen and (max-width: 1300px) {
  .fullBlock {
    .leftBlock {
      width: 100%;
      margin-right: 0 !important;
    }
  }
}
@media only screen and (max-width: 1300px) {
  .fullBlock {
    padding-top: 0 !important;
  }
}
@media only screen and (max-width: 1100px) {
  .fullBlock {
    .rightBlock {
      padding-right: 150px !important;
    }
    .leftBlock {
      padding-left: 150px !important;
    }
  }
}
@media only screen and (max-width: 700px) {
  .fullBlock {
    .rightBlock {
      padding-right: 30px !important;
    }
    .leftBlock {
      padding-left: 30px !important;
    }
  }
}
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
  padding-left: 300px;
}
.rightBlock {
  padding-right: 300px;
}

</style>
