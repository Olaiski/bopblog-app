<template>
    <div class="about-page">
      <div id="header">
        <h1> - Om oss / Prosjektet- </h1>

      </div>

      <div class="about-text">
        <p>Heisann!</p>
        <p>Vi er Anders og Tommy, vi jobber med en bachelor i IT & Informasjonssystemer ved USN Bø.</p>
        <p>Vi skal utvikle et 2D-plattform spill, valgte spill pga. interesse og utfordring....  Har utviklet en del CRUD applikasjoner i tidligere semestere,
          valgte å prøve noe helt nytt </p>

        <p>Spillet skal ha kampsystem i ekte-tid.
          Spillet skal inneholde fiender, interaktive og fiendtlige miljøobjekter og et inventarsystem.
          Level designet baserer seg på Metroidvania prinsipper.
        </p>

        <p>Oppdaterer bloggen forløpende, vises fra første til siste innlegg.. Legger til GIFs etc</p>

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
</style>
