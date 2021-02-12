<template>
  <header>
    <div class="title">2D Unity, Bachelor blog.</div>
    <nav>
        <nuxt-link to="/">
          <v-btn class="nav-btn">
            Hjem
          </v-btn>
        </nuxt-link>

      <nuxt-link to="/about">
        <v-btn class="nav-btn">
            Om Oss
        </v-btn>
      </nuxt-link>

      <nuxt-link to="/files">
        <v-btn class="nav-btn">
          Filer
        </v-btn>
      </nuxt-link>
    </nav>
  </header>
</template>

<script>
    export default {
        name: "Header"
    }
</script>

<style scoped>


  header {
    padding: 30px 30px;
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.1);
  }

  header .title {
    color: #EEE;
    font-size: 24px;
    font-weight: 900;
    text-transform: uppercase;

  }

  nav {
    display: flex;
    align-items: center;
    margin: 0 -15px;

  }

  nav a {
    display: block;
    margin: 0 15px;
    color: white;
    font-size: 20px;
  }

</style>
