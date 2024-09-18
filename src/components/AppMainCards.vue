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
                    console.log(response);
                    this.cardsList = response
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
        <div class="row">
            <div class="col-6 col-lg-3" v-for="n in 15">
                <AppMainCardsItem />
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped></style>