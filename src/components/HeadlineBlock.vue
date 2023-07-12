<template>
    <div>
      <input class="headline" type="text" v-model="headline" placeholder="Enter headline" />
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        headline: '',
      }
    }
  }
  </script>
  <style lang="scss" scoped>
  .headline {
    margin-top: 5px;
    border: none;
    width: 20%;
    height: 30px;
    font-size:25px ;
    // background-color: rgb(255, 255, 255);
  }
  </style>