<template>
    <b-row class="vlaai-row">
        <b-col><p id="naam">{{vlaai.naam}}</p></b-col>
        <b-col><p id="total">{{vlaai.winkel + vlaai.klant}}</p></b-col>
        <b-col v-bind:class="{'hidden': print_friendly}" ><b-button squared v-on:click="plusKlant"><font-awesome-icon icon="user-plus" size="2x" /></b-button></b-col>
        <b-col v-bind:class="{'hidden': print_friendly}"><b-button squared v-on:click="plusWinkel"><font-awesome-icon icon="store" size="2x" /></b-button></b-col>
        <b-col><p class="clickable" v-on:click="minKlant">{{vlaai.klant}}</p>  </b-col>
        <b-col><p class="clickable" v-on:click="minWinkel">{{vlaai.winkel}}</p></b-col>
    </b-row>
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

button {
    background-color:#64184c;
    margin:auto;
}

button:hover {
    background-color:white;
    color:#64184c
}

.vlaai-row {
    margin-top:10px;
    padding-top:10px;
    border-top:#64184c 1px solid
}
</style>