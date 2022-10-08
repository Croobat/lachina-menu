<template>
  <!-- <TheTest /> -->
  <div v-for="categorie in menu" :key="categorie.id" :categorie="categorie">
    <b>{{ categorie.name }}</b>
    <div v-for="menuItem in categorie.menuItems" :key="menuItem.id" :menuItem="menuItem">
      {{ menuItem.name }}
      <br>
      <u>{{ menuItem.description }}</u>
      <br>
      <i>{{ menuItem.price }}</i>
      <div v-for="subItem in menuItem.subItems" :key="subItem.id" :menuItem="subItem">
        {{ subItem.name }}
        <u>{{ subItem.description }}</u>
        <i>{{ subItem.price }}</i>
      </div>
      <br>
      <br>
    </div>
    <br>
    <br>
    <br>
  </div>
</template>

<script>
// import TheTest from './components/TheTest.vue'
  import menu from './assets/menu.json'

export default {
  name: 'App',
  components: {
    // TheTest
  },
  data() {
    return {
      menu: menu
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
