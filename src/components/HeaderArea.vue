<template>

  <header>
    <div id="logo">
      Boolgram
    </div>
    <div class="searchbar">
      <input type="text" name="searchbar" value="" placeholder="Cerca">
    </div>
    <div class="userinfo">
      <i class="fas fa-home"></i>
      <i class="far fa-paper-plane"></i>
      <i class="far fa-compass"></i>
      <i class="far fa-heart"></i>
      <img src="https://i.imgur.com/TXzx3Df.jpg" class="profileHead">
    </div>
  </header>

</template>

<script>

export default {
  name: 'HeaderArea',
  data: function() {
    return {
    };
  },
  props: {
  },
  methods: {
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

@media only screen and (max-width: 1100px) {
  header {
    padding: 15px 150px !important;
  }
}
@media only screen and (max-width: 800px) {
  .searchbar {
    display: none;
  }
}
@media only screen and (max-width: 700px) {
  header {
    padding: 15px 30px !important;
  }
}
@media only screen and (max-width: 500px) {
  .userinfo i {
    display: none;
  }
}
header {
  display: flex;
  justify-content: space-between;
  font-family: 'Dancing Script', cursive;
  background-color: white;
  padding: 15px 300px;
  border-bottom: solid 2px #e9e9e9;
  #logo {
    font-weight: bolder;
    font-size: 40px;
    cursor: pointer;
  }
  .searchbar {
    input {
      height: 30px;
      border: solid 2px #e9e9e9;
      text-align: center;
      margin-top: 10px;
      background-color: #fafafa;
    }
  }
  div.userinfo {
    display: flex;
    align-items: center;
    // padding-top: 14px;
    i {
      cursor: pointer;
      margin-right: 15px;
      font-size: 18px;
      &:hover {
        color: rgb(238, 39, 87);
      }
    }
    img {
      width: 32px;
      height: 32px;
      border-radius: 50%;
      cursor: pointer;
    }
  }
}

</style>
