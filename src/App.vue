<template>
  <!-- <TheTest /> -->
  <div v-for="categorie in menu" :key="categorie.id" :categorie="categorie">
    <p class="font-title_cursive">{{ categorie.name }}</p>
    <div v-for="menuItem in categorie.menuItems" :key="menuItem.id" :menuItem="menuItem">
      <div v-if="menuItem.name" class="font-title">{{ menuItem.name }}</div>
      <div v-if="menuItem.description" class="font-body">{{ menuItem.description }}</div>
      <div v-if="menuItem.price" class="font-price">{{ menuItem.price }} $</div>
      <div v-for="subItem in menuItem.subItems" :key="subItem.id" :menuItem="subItem">
        <p class="font-subBody">{{ subItem.name }}</p>
        <div v-if="subItem.description" class="font-body">{{ subItem.description }}</div>
        <div v-if="subItem.price" class="font-price">{{ subItem.price }} $</div>
      </div>
    </div>
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
@font-face {
  font-family: "Alishba";
  src: url("./assets/fonts/alishba/AlishbaRegular.otf");
}

@font-face {
  font-family: "AlishbaBold";
  src: url("./assets/fonts/alishba/AlishbaBold.otf");
}

@font-face {
  font-family: "Poppins";
  src: url("./assets/fonts/poppins/poppins-regular.ttf");
}

@font-face {
  font-family: "PoppinsSemiBold";
  src: url("./assets/fonts/poppins/poppins-semibold.ttf");
}

@font-face {
  font-family: "PoppinsBold";
  src: url("./assets/fonts/poppins/poppins-bold.ttf");
}

@font-face {
  font-family: "WinnerNarrowExtraBold";
  src: url("./assets/fonts/winnernarrow/winnernarrow-extrabold.ttf");
}

:root {
  font-size: 10px;
}

#app {
  font-family: Avenir, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

p {
  margin: 0;
  padding: 0;
}

.font-title_cursive {
  font-family: AlishbaBold;
  font-size: 5rem;
  margin-top: 4rem;
  margin-bottom: 0;
}

.font-title {
  font-family: PoppinsBold;
  font-size: 2.2rem;
  margin-top: 1rem;
}

.font-body {
  font-family: PoppinsSemiBold;
  font-size: 1.5rem;
  margin-top: 0.5rem;
}

.font-subBody {
  font-family: PoppinsSemiBold;
  font-size: 1.5rem;
}

.font-price {
  font-family: WinnerNarrowExtraBold;
  font-size: 2.5rem;
}

.test {
  border: 1px solid red;
}
</style>
