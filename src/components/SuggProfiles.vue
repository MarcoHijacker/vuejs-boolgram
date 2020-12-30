<template>

  <div class="suggprofiles">
    <ul>
      <li>
        <img src="https://i.imgur.com/TXzx3Df.jpg" class="profileOwn">
        <div class="ownerInfo">
          <span>tidus.ffx</span><br>
          <span class="realName">Tidus Shuyin</span>
        </div>
        <a href='#' class="followhim">Passa</a>
      </li>
      <li class="suggbar">Suggerimenti per te:</li>
      <li v-for="(profile, idx) in profiles" :key="idx">
        <img v-bind:src="profile.profile_picture" class="profileImg">
        <div class="suggNicknames" v-text="profile.profile_name"></div>
        <a href='#' class="followhim">Segui</a>
      </li>
      <li class="copyright">&copy; 2020 Instagram from Facebook.</li>
    </ul>
  </div>

</template>

<script>

import axios from 'axios';
export default {
  name: 'SuggProfiles',
  data: function() {
    return {
      profiles: null,
    };
  },
  mounted: function() {
    axios.get('https://flynn.boolean.careers/exercises/api/boolgram/profiles')
      .then(response => this.profiles = response.data)
      .finally(() => console.log('Profiles Data loading completed.'));
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
ul {
  list-style-type: none;
  padding: 0;
}
/* Custom */
img {
  width: 32px;
  height: 32px;
  border-radius: 50%;
}
ul {
  li {
      display: flex;
      justify-content: flex-start;
      align-items: center;
      margin: 10px 0;
      img {
        margin: 0 7px;
        cursor: pointer;
      }
      div {
        font-size: 13px;
        font-weight: bold;
        width: 170px;
        text-align: left;
      }
      a {
        text-decoration: none;
        color: #7bbaf7;
        font-size: 13px;
        font-weight: bolder;
        &:hover {
          color: #547ea7;
        }
      }
      img.profileOwn {
        width: 64px;
        height: 64px;
      }
      span.realName {
        font-weight: normal;
        color: darkgrey;
      }
      div.ownerInfo {
        width: 137px;
        padding-left: 15px;
      }
      div.suggNicknames {
        padding-left: 10px;
      }
    }
    li.suggbar {
      font-size: 13px;
      font-weight: bold;
      margin: 20px 0;
      color: darkgrey;
    }
    li.copyright {
      font-size: 13px;
      margin: 40px 0;
      color: darkgrey;
    }
  }
  
</style>
