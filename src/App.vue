<template>
  <div>
    <HeroImage />
  </div>
  <Text />
</template>

<script>
import HeroImage from "./components/HeroImage.vue";
import Text from "./components/Text.vue";

export default {
  name: "App",
  components: {
    HeroImage,
    Text,
  },
};
</script>

<style>
#app {
  min-width: 18.75rem;
  max-width: 45.625rem;
  width: 100%;
  height: fit-content;
  margin: 0rem 1.5rem;
  background-color: hsl(0, 0%, 100%);
  box-shadow: 0rem 2.5rem 2.5rem -0.625rem rgba(201, 213, 225, 0.503415);
  border-radius: 0.625rem;
}

@media screen and (min-width: 600px) {
  #app {
    display: flex;
  }
}
</style>
