<template>
    <header>
        <input type="text" placeholder="Title" v-model="userSearch">
        <button @click="$emit('getUserSearch', userSearch)">
            Search
        </button>
    </header>
</template>

<script>
export default {
    name: "Header",
    data: function() {
        return {
            userSearch: ""
        }
    }
}
</script>

<style lang="scss" scoped>
header {
    height: 50px;
    background-color: gray;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>