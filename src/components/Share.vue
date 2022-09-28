<template>
  <div class="main-container">
    <div class="share-icons">
      <p class="share-text">Share</p>
      <img :src="facebook" alt="Facebook Icon" />
      <img :src="twitter" alt="Twitter Icon" />
      <img :src="pinterest" alt="Pinterest Icon" />
    </div>
    <div class="share-icon" @click="toggleShareOff">
      <img :src="shareWhite" alt="Share Icon" class="icon-white" />
    </div>
  </div>
</template>

<script>
import shareWhite from "/src/assets/images/icon-share-white.svg";
import facebook from "/src/assets/images/icon-facebook.svg";
import twitter from "/src/assets/images/icon-twitter.svg";
import pinterest from "/src/assets/images/icon-pinterest.svg";

export default {
  data() {
    return {
      facebook: facebook,
      twitter: twitter,
      pinterest: pinterest,
      shareWhite: shareWhite,
    };
  },
  methods: {
    toggleShareOff() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.main-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: var(--very-dark-gray-blue);
  padding: 22px 32px;
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
}

.share-icons {
  width: 100%;
  display: flex;
  justify-content: space-between;
}

.share-text {
  line-height: 20px;
  letter-spacing: 5px;
  color: var(--gray-blue);
  text-transform: uppercase;
}

.share-icons img {
  width: 20px;
  height: 20px;
}

.share-icons img:hover {
  cursor: pointer;
}

.share-icon {
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  background-color: var(--desaturated-dark-blue);
  padding: 10px;
  margin-left: 56px;
}

.share-icon:hover {
  cursor: pointer;
}

.icon-white {
  width: 15px;
  height: 15px;
}
</style>