<script>

import AppMainSelect from './AppMainSelect.vue';
import AppMainCards from './AppMainCards.vue';
import axios from 'axios';

export default {
    data() {
        return {
            cardsList: [],
            apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0",
            archetypesList: [],
            archetypeUrl: "https://db.ygoprodeck.com/api/v7/archetypes.php"
        }
    },
    methods: {
        // Chiamata API
        getCards() {
            axios.get(this.apiUrl)
                .then((response) => {
                    // handle success
                    console.log(response.data.data);
                    this.cardsList = response.data.data;
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        },
        getArchetype() {
            axios.get(this.archetypeUrl)
                .then((response) => {
                    console.log(response.data)
                    this.archetypesList = response.data;
                });
        }

    },
    components: {
        AppMainSelect,
        AppMainCards
    },
    created() {
        this.getCards();
        this.getArchetype();
    }

}
</script>

<template>
    <main class="py-4">
        <AppMainSelect />
        <AppMainCards :cards="cardsList" />
    </main>
</template>

<style lang="scss" scoped>
main {
    background-color: #D48F3B;
}
</style>