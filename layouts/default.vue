<template>
  <div>

    <Header />

    <Nuxt />

  </div>
</template>

<script>
import Header from "../components/Header";
export default {
  components: {Header},
}
</script>

<style>

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Roboto, sans-serif;
  }

  body {
    background-color: #EEE;
  }

  a {
    text-decoration: none;
  }

  p {
    margin-bottom: 15px;
  }
  p:last-of-type {
    margin-bottom: 0;
  }
</style>
