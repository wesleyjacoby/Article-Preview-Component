<template>
  <img :src="image" alt="Desk of Drawers" class="main-image" />
</template>

<script>
import image from "/src/assets/images/drawers.jpg";

export default {
  data() {
    return {
      image: image,
    };
  },
};
</script>

<style scoped>

.main-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
}

@media screen and (min-width: 600px) {
  .main-image {
    height: 100%;
    border-bottom-left-radius: 10px;
    border-top-right-radius: 0px;
  }
}
</style>