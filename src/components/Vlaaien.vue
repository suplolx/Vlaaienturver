<template>
    <div class="container">
        <Header/>
        <input v-on:change="togglePrint" type="checkbox">
        <div class="grid-thing">
            <p>Vlaaien</p>
            <p>Totaal</p>
            <p></p>
            <p></p>
            <p>Klant</p>
            <p>Winkel</p>
        </div>

        <div v-if="print_friendly == true">
            <div v-bind:key="vlaai.id" v-for="vlaai in vlaaien">
                <Vlaai v-bind:vlaai="vlaai" v-if="vlaai.winkel + vlaai.klant > 0"/>
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

p {
    margin:auto;
    font-size: 18px;
}

.container {
    margin-top:40px;
    max-width: 1060px;
}

</style>