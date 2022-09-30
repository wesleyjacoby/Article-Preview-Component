<template>
  <div class="main-container">
    <div class="share-icons">
      <p class="share-text">Share</p>
      <img :src="facebook" alt="Facebook Icon" class="facebook" />
      <img :src="twitter" alt="Twitter Icon" class="twitter" />
      <img :src="pinterest" alt="Pinterest Icon" class="pinterest" />
    </div>
  </div>
</template>

<script>
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
};
</script>

<style scoped>
.main-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: var(--very-dark-gray-blue);
  width: 248px;
  height: 67px;
  border-radius: 10px;
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
  animation: bounce-bottom 0.9s both;
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

.pointer {
  display: none;
}

@keyframes bounce-bottom {
  0% {
    transform: translateY(10px);
    animation-timing-function: ease-in;
    opacity: 1;
  }
  24% {
    opacity: 1;
  }
  40% {
    transform: translateY(5px);
    animation-timing-function: ease-in;
  }
  65% {
    transform: translateY(3px);
    animation-timing-function: ease-in;
  }
  82% {
    transform: translateY(2px);
    animation-timing-function: ease-in;
  }
  93% {
    transform: translateY(1px);
    animation-timing-function: ease-in;
  }
  25%,
  55%,
  75%,
  87% {
    transform: translateY(0px);
    animation-timing-function: ease-out;
  }
  100% {
    transform: translateY(0px);
    animation-timing-function: ease-out;
    opacity: 1;
  }
}
</style>