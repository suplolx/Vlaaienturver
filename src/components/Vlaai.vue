<template>
        <div class="grid-thing">
            <p>{{vlaai.naam}}</p>
            <p id="total">{{vlaai.winkel + vlaai.klant}}</p>
            <button v-on:click="plusKlant"><font-awesome-icon icon="user-plus" size="2x" /></button>
            <button v-on:click="plusWinkel"><font-awesome-icon icon="store" size="2x" /></button>
            <p v-on:click="minKlant">{{vlaai.klant}}</p>  
            <p v-on:click="minWinkel">{{vlaai.winkel}}</p>
        </div>
</template>

<script>
export default {
    name: "Vlaai",
    props: ["vlaai"],
    methods: {
        plusWinkel() {
            this.vlaai.winkel = this.vlaai.winkel + 1;
        },

        plusKlant() {
            this.vlaai.klant = this.vlaai.klant + 1;
        },

        minWinkel() {
            this.vlaai.winkel = this.vlaai.winkel - 1;
        },

        minKlant() {
            this.vlaai.klant = this.vlaai.klant - 1;
        },
    }
}
</script>

<style scoped>
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
</style>