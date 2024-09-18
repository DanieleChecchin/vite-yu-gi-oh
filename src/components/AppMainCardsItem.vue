<script>

export default {
    data() {
        return {

        }
    },
    props: {
        cardObject: {
            type: Object,
            required: true
        }
    }
}
</script>

<template>
    <div class="col">
        <article class="card my-3 text-white">
            <img :src="cardObject.card_images.image_url" class="card-img-top" alt="...">
            <div class="card-body">
                <h5 class="card-title"> {{ cardObject.name }} </h5>
                <p class="card-text"> Alien </p>
            </div>
        </article>
    </div>
</template>

<style lang="scss" scoped>
.col {
    flex-basis: calc(100% / 5);
}

.card {
    background-color: #D48F3B;
}
</style>