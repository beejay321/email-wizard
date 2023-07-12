<template>
  <div class="imageDiv">
    <input
      type="url"
      v-model="imageUrl"
      placeholder="Enter image URL"
      class="imageUrl"
    />
    <img :src="imageUrl" v-if="imageUrl" class="image" />
    <textarea class="text-area" v-model="text" placeholder="Enter text" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      imageUrl: "",
      text: "",
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
.text-area {
  margin-top: 5px;
  border: none;
  width: 50%;
  background-color: rgb(255, 255, 255);
}
</style>
