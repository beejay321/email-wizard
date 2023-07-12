<template>
  <div>
    <textarea class="text-area" v-model="text" placeholder="Enter text" />
  </div>
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
</style>
