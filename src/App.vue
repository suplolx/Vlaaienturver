<template>
  <div id="app">
      <Header v-bind:print_friendly="print_friendly"/>
      <b-container>
        <label class="switch">
          <input v-on:change="togglePrint" type="checkbox">
          <span class="slider round"></span>
      </label>
      </b-container>
      <Vlaaien :vlaaien="vlaaien" :print_friendly="print_friendly"/>
  </div>
</template>

<script>
import Vlaaien from './components/Vlaaien'
import Header from './components/Header'

export default {
  name: 'app',
  components: {
    Vlaaien,
    Header,
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
  },
  methods: {
        togglePrint () {
            this.print_friendly = !this.print_friendly;
        },
  }
}
</script>

<style>
/* @import url('./assets/normalize.css');
@import url('./assets/skeleton.css'); */

body{
  background:#fffae8;
}

.hidden {
    display: none;
}

.show {
    display:inline-block;
}

.switch {
  position: relative;
  display: inline-block;
  width: 50px;
  height: 24px;
}

.switch input { 
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: .4s;
  transition: .4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 16px;
  width: 16px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: .4s;
  transition: .4s;
}

input:checked + .slider {
  background-color: #64184c;
}

input:focus + .slider {
  box-shadow: 0 0 1px #64184c;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}
</style>
