<template>
  <div id="app">
      <Vlaaien :vlaaien="vlaaien" :print_friendly="print_friendly"/>
  </div>
</template>

<script>
import Vlaaien from './components/Vlaaien'

export default {
  name: 'app',
  components: {
    Vlaaien,
  },
  data() {
    return {
      print_friendly: false,
      vlaaien: [
        {
          id: 1,
          naam: "Kersenvlaai",
          winkel: 0,
          klant: 0,
        },
        {
          id: 2,
          naam: "Abrikozenvlaai",
          winkel: 0,
          klant: 0,
        },
        {
          id: 3,
          naam: "Appelvlaai",
          winkel: 0,
          klant: 0,
        },
        {
          id: 4,
          naam: "Appel krokant",
          winkel: 0,
          klant: 0,
        },
        {
          id: 5,
          naam: "Appel toeslag",
          winkel: 0,
          klant: 0,
        },
        {
          id: 6,
          naam: "Weerter Appel",
          winkel: 0,
          klant: 0,
        },
        {
          id: 7,
          naam: "Zwartepruimenvlaai",
          winkel: 0,
          klant: 0,
        },
        {
          id: 8,
          naam: "Pudding kruimel",
          winkel: 0,
          klant: 0,
        },
        {
          id: 9,
          naam: "Abrikoos kruimel",
          winkel: 0,
          klant: 0,
        },
        {
          id: 10,
          naam: "Kersen kruimel",
          winkel: 0,
          klant: 0,
        },
        {
          id: 11,
          naam: "Appel kruimel",
          winkel: 0,
          klant: 0,
        },
        {
          id: 12,
          naam: "Appeltaart",
          winkel: 0,
          klant: 0,
        },
        {
          id: 13,
          naam: "Linzen abrikoos",
          winkel: 0,
          klant: 0,
        },
        {
          id: 14,
          naam: "Linzen kersen",
          winkel: 0,
          klant: 0,
        },
        {
          id: 15,
          naam: "Linzen Appel",
          winkel: 0,
          klant: 0,
        },
        {
          id:16,
          naam: "Rijstevlaai",
          winkel: 0,
          klant: 0,
        },
        {
          id: 17,
          naam: "Kersen speicaal",
          winkel: 0,
          klant: 0,
        },
        {
          id: 18,
          naam: "Abrikozen speciaal",
          winkel: 0,
          klant: 0,
        },
        {
          id: 19,
          naam: "Kruisbessen schuim",
          winkel: 0,
          klant: 0,
        },
        {
          id:20,
          naam: "Aardbeien (harde bodem)",
          winkel: 0,
          klant: 0,
        },
        {
          id:21,
          naam: "Abrikoos slagroom (harde bodem)",
          winkel: 0,
          klant: 0,
        },
        {
          id:22,
          naam: "Belgische room",
          winkel: 0,
          klant: 0,
        },
        {
          id: 23,
          naam: "Bienestisch",
          winkel: 0,
          klant: 0,
        },
        {
          id: 24,
          naam: "Rijstevlaai slagroom",
          winkel: 0,
          klant: 0,
        },
        {
          id: 25,
          naam: "Slagroomtaart",
          winkel: 0,
          klant: 0,
        },

      ]
    }
  }
}
</script>

<style>
@import url('./assets/normalize.css');
@import url('./assets/skeleton.css');

#app {
  font-weight:bolder;
}

body{
  background:#fffae8;
}

</style>
