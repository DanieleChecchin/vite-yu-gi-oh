<script>

export default {
    data() {
        return {

        }
    },
    props: {
        archetypes: {
            type: Array,
            required: true
        }
    }

}
</script>

<template>
    <div class="select container">
        <select class="form-select" @change="$emit('logCiao')" aria-label="Default select example">
            <option selected>Choose an archetype</option>
            <option v-for="(archetype, index) in archetypes" :key="index" value="1"> {{ archetype.archetype_name }}
            </option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
select {
    width: 200px;
}
</style>