<script>

export default {
    data() {
        return {
            optionSelected: '',
        }
    },
    props: {
        archetypes: {
            type: Array,
            required: true
        }
    },
    methods: {
        changeEvent() {
            this.$emit('chooseArchetype', this.optionSelected);
        }
    }

}
</script>

<template>
    <div class="select container">
        <select class="form-select" @change="changeEvent" v-model="optionSelected">
            <option selected>Choose an archetype</option>
            <option v-for="(archetype, index) in archetypes" :key="index" :value="archetype.archetype_name"> {{
                archetype.archetype_name }}
            </option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
select {
    width: 200px;
}
</style>