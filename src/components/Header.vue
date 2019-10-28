<template>
    <b-container>
        <b-row>
            <b-col><h1>Vlaaienturver</h1></b-col>
            <b-col cols="9" class="hidden" v-bind:class="{'show': print_friendly}"><b-button variant="outline-info" v-on:click="printPage"><font-awesome-icon icon="print" size="2x" /></b-button></b-col>
            <b-col v-bind:class="{'hidden': print_friendly}"><img width="25%" src="../assets/b_logo.png" alt=""></b-col>
        </b-row>
        <b-row v-bind:class="{'print': print_friendly}">
            <b-col><p>Vlaaien</p></b-col>
            <b-col><p>Totaal</p></b-col>
            <b-col v-bind:class="{'hidden': print_friendly}"><p></p></b-col>
            <b-col v-bind:class="{'hidden': print_friendly}"><p></p></b-col>
            <b-col><p>Klant</p></b-col>
            <b-col><p>Winkel</p></b-col>
        </b-row>
    </b-container>
</template>

<script>
export default {
    name: "Header",
    props:["print_friendly"],
    methods: {
        printPage() {
            window.print();
        },
    }

}
</script>

<style scoped>

p {
    font-size:22px;
    font-weight:500;
}

img {
    margin-left:60%;
}

h1 {
    margin-top:25px;
}

.row {
    margin-top:25px;
}

button {
    margin-top:30px;
}
</style>