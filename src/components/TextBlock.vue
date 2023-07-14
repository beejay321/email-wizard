<template>
  <textarea
    class="text-area"
    cols="30"
    rows="10"
    v-model="text"
    placeholder="Enter text"
  />
</template>

<script>
export default {
  data() {
    return {
      text: "",
    };
  },
};
</script>
<style lang="scss" scoped>
.text-area {
  margin-top: 5px;
  border: none;
  width: 50%;
  background-color: rgb(255, 255, 255);
}
.text-area:hover {
  border: 2px solid rgb(130, 130, 130);
}
</style>
