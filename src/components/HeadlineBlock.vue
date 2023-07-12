<template>
  <div>
    <input
      class="headline"
      type="text"
      v-model="headline"
      placeholder="Enter headline"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      headline: "",
    };
  },
};
</script>
<style lang="scss" scoped>
.headline {
  margin-top: 5px;
  border: none;
  height: 30px;
  min-width: auto;
  font-size: 25px;
  // background-color: rgb(255, 255, 255);
}
</style>
