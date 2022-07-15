<template>
  <footer>
    <ul>
      <li>Informazioni</li>
      <li>Blog</li>
      <li>Lavora con noi</li>
      <li>Assistenza</li>
    </ul>
    <ul>
      <li>Italiano <i class="fas fa-caret-down"></i></li>
      <li>&copy; 2021 Instagram di Facebook</li>
    </ul>
  </footer>
</template>

<script>
export default {
  name: "FooterArea",
  data: function () {
    return {};
  },
  props: {},
  methods: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
footer {
  height: 80px;
  border-top: solid 1px #cecece;
  margin-top: 50px;
  color: darkgrey;
  font-size: 13px;
}
footer ul {
  margin: 15px 0;
}
footer ul li {
  display: inline-block;
  margin: 0 10px;
  cursor: pointer;
}
</style>
