<script>

import AppMainCardsItem from './AppMainCardsItem.vue';
import axios from 'axios';

export default {
    data() {
        return {
            cardsList: [],
            apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0"
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
        }

    },
    components: {
        AppMainCardsItem
    },
    created() {
        this.getCards();
    }
}
</script>

<template>
    <section class="container mt-4 bg-white p-5">
        <div class="counter text-white p-3 fw-bold"> Found {{ cardsList.length }} cards </div>
        <div class="row">
            <AppMainCardsItem v-for="card in cardsList" :key="card.id" :cardObject="card" />
        </div>
    </section>
</template>

<style lang="scss" scoped>
.counter {
    background-color: #212429;
}
</style>