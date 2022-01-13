<template>
  <header>
    <h2>BOOLFLIX</h2>
    <div>
      <input type="text" placeholder="Title" v-model="userSearch" />
      <button @click="$emit('getUserSearch', userSearch)">Search</button>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  data: function () {
    return {
      userSearch: "",
    };
  },
};
</script>

<style lang="scss" scoped>
header {
  height: 80px;
  padding: 10px;
  background-color: #303030;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: fixed;
  width: 100%;
  z-index: 10;

  h2 {
    color: red;
  }
}
</style>