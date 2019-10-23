<template>
    <div class="container">
        <Header/>
        <label class="switch">
            <input v-on:change="togglePrint" type="checkbox">
            <span class="slider round"></span>
        </label>
        <button class="hidden" v-bind:class="{'show': print_friendly}" v-on:click="printPage"><font-awesome-icon icon="print" size="2x" /></button>
        <div v-bind:class="{'print': print_friendly}" class="grid-thing">
            <p>Vlaaien</p>
            <p>Totaal</p>
            <p v-bind:class="{'hidden': print_friendly}"></p>
            <p v-bind:class="{'hidden': print_friendly}"></p>
            <p>Klant</p>
            <p>Winkel</p>
        </div>

        <div v-if="print_friendly == true">
            <div v-bind:key="vlaai.id" v-for="vlaai in vlaaien">
                <Vlaai :print_friendly="print_friendly" v-bind:vlaai="vlaai" v-if="vlaai.winkel + vlaai.klant > 0"/>
            </div>
        </div>
        <div v-else>
            <div v-bind:key="vlaai.id" v-for="vlaai in vlaaien">
                <Vlaai v-bind:vlaai="vlaai"/>
            </div>
        </div>
        
    </div>
</template>

<script>
import Vlaai from './Vlaai'
import Header from './Header'

export default {
    name: "Vlaaien",
    components: {
        Vlaai,
        Header
    },
    props:["vlaaien", "print_friendly"],
    methods: {
        togglePrint () {
            this.print_friendly = !this.print_friendly;
        },

        printPage() {
            window.print();
        },
    }
}
</script>

<style scoped>

button {
    position: relative;
    margin:0 10px 0 10px;
    background-color:#64184c;
    color:white;
}

button:hover {
    color:#64184c!important;
    background-color:white!important;
}

button:focus {
    color:white;
    background-color:#5c2b4c;
}

.grid-thing {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    padding:10px;
    border-bottom: 1px solid #64184c;
}

.print {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    padding:10px;
    border-bottom: 1px solid #64184c;
}

p {
    margin:auto;
    font-size: 18px;
}

.container {
    margin-top:40px;
    max-width: 1060px;
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

.hidden {
    display: none;
}

.show {
    display:inline-block;
}

</style>