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
    <main class="py-4">
        <AppMainSelect />
        <AppMainCards />
    </main>
</template>

<style lang="scss" scoped>
main {
    background-color: #D48F3B;
}
</style>