<template>
  <Header title="Convertisseur Salaire"></Header>
  <container></container>
</template>

<script>
import Header from "./components/Header.vue";
import Container from "./components/Container.vue";
export default {
  components: {
    Header,
    Container,
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");

* {
  box-sizing: border-box;
}

html {
  font-family: "Roboto", sans-serif;
}

body {
  margin: 0;
}
</style>
