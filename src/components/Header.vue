<template>
    <header>
        <input type="text" placeholder="Title">
        <button>Search</button>
    </header>
</template>

<script>
export default {
    name: "Header"
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