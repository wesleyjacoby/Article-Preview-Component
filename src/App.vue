<template>
  <HeroImage />
  <Text />
  <Author />
</template>

<script>
import HeroImage from "./components/HeroImage.vue";
import Text from "./components/Text.vue";
import Author from "./components/Author.vue";

export default {
  name: "App",
  components: {
    HeroImage,
    Text,
    Author,
  },
};
</script>

<style>
#app {
  min-width: 280px;
  width: 100%;
  height: fit-content;
  margin: 0px 24px;
  background-color: hsl(0, 0%, 100%);
  box-shadow: 0px 40px 40px -10px rgba(201, 213, 225, 0.503415);
  border-radius: 10px;
}
</style>
