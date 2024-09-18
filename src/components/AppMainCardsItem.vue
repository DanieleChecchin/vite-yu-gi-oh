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
        <article class="card my-3 text-center ">
            <img :src="cardObject.card_images[0].image_url" class="card-img-top" alt="Card image">
            <div class="card-body">
                <h5 class="card-title text-white"> {{ cardObject.name }} </h5>
                <p class="card-text"> {{ cardObject.archetype }} </p>
            </div>
        </article>
    </div>
</template>

<style lang="scss" scoped>
.col {
    flex-basis: 20%;
}

.card {
    background-color: #D48F3B;
    height: 400px;

}
</style>