<script>

import AppMainCardsItem from './AppMainCardsItem.vue';
import axios from 'axios';

export default {
    data() {
        return {

        }
    },
    components: {
        AppMainCardsItem
    },
    props: {
        cards: {
            type: Array,
            required: true
        }
    }
}
</script>

<template>
    <section class="container mt-4 bg-white p-5">
        <div class="counter text-white p-3 fw-bold"> Found {{ cards.length }} cards </div>
        <div class="row">
            <AppMainCardsItem v-for="card in cards" :key="card.id" :cardObject="card" />
        </div>
    </section>
</template>

<style lang="scss" scoped>
.counter {
    background-color: #212429;
}
</style>