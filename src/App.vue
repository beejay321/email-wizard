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
}

.container {
  max-width: 900px;
  margin: 0 auto;
  width: 100vw;
  height: 100vh;
  border: 1px solid rgb(221, 221, 221);
  border-radius: 15px;
  background-color: rgb(255, 255, 255);
}
</style>
