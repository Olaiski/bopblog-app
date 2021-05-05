<template>
  <div class="about-page">
    <div id="header">
      <h1> - Her finner du link til spillet - </h1>

    </div>

    <div class="about-text">
      <p>Første load har en liten bug (Healthbar viser 0% helse).</p>
      <p>Dette er fordi spillet er ment for windows, og spillet prøver å laste inn fra fil. Men denne versjonen kjører det i nettleseren og finner da ikke filen.</p>

    </div>

    <div class="about-text" id="link">
      <a href="https://play.unity.com/mg/other/roguevania" target="_blank">Klikk her!</a>
    </div>




  </div>
</template>


<script>
  export default {
    name: "about"
  }
</script>

<style scoped>

  #header {
    padding-top: 50px;
    text-align: center;

  }

  #header h1 {
    font-size: 50px;
    font-weight: lighter;
  }

  .about-text {
    margin: 0 auto;
    width: 50%;
  }

  #link {
    font-size: 20px;
    margin-top: 50px;
  }
</style>
