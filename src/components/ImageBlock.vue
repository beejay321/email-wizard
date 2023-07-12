<template>
  <div class="imageDiv">
    <input
      type="url"
      v-model="imageUrl"
      placeholder="Enter image URL"
      class="imageUrl"
    />
    <img :src="imageUrl" v-if="imageUrl" class="image" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      imageUrl: "",
    };
  },
};
</script>
<style lang="scss" scoped>
.imageDiv {
  display: flex;
  flex-direction: column;
}
.imageUrl {
  margin-top: 5px;
  height: 30px;
  border: none;
}
.image {
  margin-top: 5px;
  border: none;
  background-color: rgb(255, 255, 255);
}
</style>
