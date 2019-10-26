<template>
    <div>
        <b-container v-if="print_friendly == true">        
            <div v-bind:key="vlaai.id" v-for="vlaai in vlaaien">
                <Vlaai :print_friendly="print_friendly" v-bind:vlaai="vlaai" v-if="vlaai.winkel + vlaai.klant > 0"/>
            </div>
        </b-container>

        <b-container v-else>
            <div v-bind:key="vlaai.id" v-for="vlaai in vlaaien">
                <Vlaai v-bind:vlaai="vlaai"/>
            </div>
        </b-container>
    </div>
</template>

<script>
import Vlaai from './Vlaai'

export default {
    name: "Vlaaien",
    components: {
        Vlaai,
    },
    props:["vlaaien", "print_friendly"],
}
</script>

<style scoped>

</style>