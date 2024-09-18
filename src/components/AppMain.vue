<script>

import AppMainSelect from './AppMainSelect.vue';
import AppMainCards from './AppMainCards.vue';

export default {
    data() {
        return {

        }
    },
    components: {
        AppMainSelect,
        AppMainCards
    }

}
</script>

<template>
    <div>
        <h1>Main</h1>
    </div>
    <AppMainSelect />
    <AppMainCards />
</template>

<style lang="scss" scoped></style>