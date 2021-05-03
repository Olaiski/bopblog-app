<template>

  <div class="files-page">
    <div id="header">
      <h1> - Diverse prosjekt filer - </h1>

    </div>

    <div class="about-text">
      <p>Her finner man filer som er en del av prosjektet</p>
    </div>


    <div class="dl-grid">

      <v-simple-table class="v-table"
        fixed-header
      >
        <template v-slot:default>
          <thead>
          <tr >
            <th class="text-left">
              Fil
            </th>
            <th class="text-left">
              Docs / PDF
            </th>
          </tr>
          </thead>
          <tbody>
          <tr
            v-for="item in filer"
            :key="item.name"
          >
            <td>{{ item.name }}</td>
            <td> <a :href="item.link" target="_blank">Link</a></td>
          </tr>
          </tbody>
        </template>
      </v-simple-table>


    </div>

  </div>
</template>

<script>
    export default {
        name: "files",

        data () {
          return {
            filer: [
              {
                name: 'Prosjektskisse',
                link: "https://drive.google.com/file/d/12j47qopHTUMKk_2jhHMl0lhSGhTgwOmw/view?usp=sharing",
              },
              {
                name: 'Prosjektbeskrivelse',
                link: "https://drive.google.com/file/d/1i7AsqCeClg8dlQb-NQR2RfIJxBVZApIZ/view?usp=sharing",
              },

              {
                name: 'Prosjektkonsept',
                link: "https://drive.google.com/file/d/13S0oqC3fZgfFbANlmvjAXBbzuWWzN-t0/view?usp=sharing",
              },

              {
                name: 'Presentasjon 1 (Milepæle 1)',
                link: "https://mega.nz/file/rtoAQb6K#4VPQAnTJOz8z85HevfIAIacWBJSaMonLF6kQ9-HXhxI",
              },

              {
                name: 'Presentasjon 2 (Milepæle 2)',
                link: "https://mega.nz/file/mlh1HC6Q#z4mLN0gGTZ_LEPIaSBYY62MmOmct28FBL9F8O4eUkCU",
              },

              {
                name: 'Milepæl 3',
                link: "https://mega.nz/file/G0hzyQBQ#rbhOtHzR5JHyoG_qacQz3KabWBMDQz7FYbJs34CBTPI",
              },

            ],
          }
        }
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
    text-align: center;
  }

  .dl-grid {
    width: 800px;
    margin: 0 auto;
    text-align: center;
    padding: 5% 0 0 0;
  }


  .v-table tr:hover:not(.v-table__expanded__content) {
    background: white !important;
  }

</style>
