<template>

  <div class="suggStories">
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

@media only screen and (max-width: 1750px) {
  .suggStories {
    li:nth-last-child(-n+1) {
      display: none;
    }
  }
}
@media only screen and (max-width: 1670px) {
  .suggStories {
    li:nth-last-child(-n+2) {
      display: none;
    }
  }
}
@media only screen and (max-width: 1590px) {
  .suggStories {
    li:nth-last-child(-n+3) {
      display: none;
    }
  }
}
@media only screen and (max-width: 1510px) {
  .suggStories {
    li:nth-last-child(-n+4) {
      display: none;
    }
  }
}
@media only screen and (max-width: 1430px) {
  .suggStories {
    li:nth-last-child(-n+5) {
      display: none;
    }
  }
}
@media only screen and (max-width: 1300px) {
  .suggStories {
    margin-right: 0 !important;
    display: none;
  }
}
@media only screen and (max-width: 990px) {
  .suggStories {
    display: none;
  }
}
h3 {
  margin: 40px 0 0;
}
div.suggStories {
  padding: 50px 60px;
  background-color: white;
  border: solid 2px #e9e9e9;
  border-radius: 2px;
  margin-right: 30px;
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
