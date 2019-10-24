<template>
        <div v-bind:class="{'print': print_friendly}" class="grid-thing">
            <p id="naam">{{vlaai.naam}}</p>
            <p id="total">{{vlaai.winkel + vlaai.klant}}</p>
            <button v-bind:class="{'hidden': print_friendly}" v-on:click="plusKlant"><font-awesome-icon icon="user-plus" size="2x" /></button>
            <button v-bind:class="{'hidden': print_friendly}" v-on:click="plusWinkel"><font-awesome-icon icon="store" size="2x" /></button>
            <p class="clickable" v-on:click="minKlant">{{vlaai.klant}}</p>  
            <p class="clickable" v-on:click="minWinkel">{{vlaai.winkel}}</p>
        </div>
</template>

<script>
export default {
    name: "Vlaai",
    props: ["vlaai", "print_friendly"],
    methods: {
        plusWinkel() {
            this.vlaai.winkel++;
        },

        plusKlant() {
            this.vlaai.klant++;
        },

        minWinkel() {
            this.vlaai.winkel--;
        },

        minKlant() {
            this.vlaai.klant--;
        },
    }
}
</script>

<style scoped>
#naam {
    margin-left:0 !important;
}

.clickable {
    cursor: pointer;
}

.grid-thing {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    padding:10px;
    border-bottom: 1px solid #64184c;
}

button {
    margin:auto;
    background-color:#64184c;
    color:white;
    box-shadow: 0 4px rgb(202, 202, 202);
}

button:hover {
    color:#64184c!important;
    background-color:white!important;
}

button:focus {
    color:white;
    background-color:#5c2b4c;
}

button:active {
  background-color: #3e8e41;
  box-shadow: 0 1px #666;
  transform: translateY(4px);
}

p {
    margin:auto;
    font-size: 16px;
}

#total {
    font-size:24px;
}

.hidden {
    display: none;
}
</style>