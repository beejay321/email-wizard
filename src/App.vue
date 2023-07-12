<template>
  <div id="app" class="container">
    <EmailWizard />
  </div>
</template>

<script>
import EmailWizard from "./components/EmailWizard.vue";

export default {
  components: {
    EmailWizard,
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Fasthand&family=Rubik:wght@300&display=swap");

* {
  font-family: "Rubik", sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  max-width: 900px;
  margin: 0 auto;
  width: 100vw;
  background-color: rgb(245, 245, 245);
}
</style>
