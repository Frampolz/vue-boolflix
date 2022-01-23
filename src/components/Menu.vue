<template>
  <ul class="menu">
    <li><a href="">home</a></li>
    <li><a href="">serie tv</a></li>
    <li><a href="">film</a></li>
    <li><a href="">original</a></li>
    <li><a href="">aggiunti di recente</a></li>
    <li><a href="">la mia lista</a></li>
  </ul>
</template>

<script>
export default {
  name: "Menu",
};
</script>

<style lang="scss">
.menu {
  display: inline-block;
  margin-left: 1.5em;

  li {
    display: inline-block;
    margin: 0.3em;
    & a {
      font-size: 0.9em;
      text-decoration: none;
      text-transform: capitalize;
      font-weight: bold;
      color: rgb(148, 148, 148);
      &:hover {
        color: white;
      }
    }
  }
}
</style>
