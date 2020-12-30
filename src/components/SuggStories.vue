<template>

  <div class="suggstories">
    <ul>
      <li v-for="(profile, idx) in profiles" :key="idx">
        <img v-bind:src="profile.profile_picture" class="profileImg"> <br>
        <div class="featuredStories" v-text="profile.profile_name"></div>
      </li>
    </ul>
  </div>

</template>

<script>

import axios from 'axios';
export default {
  name: 'SuggStories',
  data: function() {
    return {
      profiles: null,
    };
  },
  mounted: function() {
    axios.get('https://flynn.boolean.careers/exercises/api/boolgram/profiles')
      .then(response => this.profiles = response.data)
      .finally(() => console.log('Stories Data loading completed.'));
  },
  props: {
  },
  methods: {
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

h3 {
  margin: 40px 0 0;
}
div.suggstories {
  padding: 50px 60px;
  background-color: white;
  border: solid 2px #e9e9e9;
  border-radius: 2px;
  margin-right: 50px;
  ul {
    list-style-type: none;
    padding: 0;
    li {
      display: inline-block;
      margin-right: 3px;
      div.featuredStories {
        font-size: 12px;
        font-weight: bold;
      }
    }
  }
  img {
    width: 64px;
    height: 64px;
    border-radius: 50%;
    border: solid 3px #d55761;
    padding: 2px;
    margin: 0 10px;
    cursor: pointer;
  }
}

</style>
