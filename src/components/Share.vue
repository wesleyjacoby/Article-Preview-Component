<template>
<transition mode="out-in"
 enter-active-class="animate__animated animate__fadeIn"
 leave-active-class="animate__animated animate__fadeOut">
  <div class="share-container">
    <div class="share-icons">
      <p class="share-text">Share</p>
      <img :src="facebook" alt="Facebook Icon" class="facebook" />
      <img :src="twitter" alt="Twitter Icon" class="twitter" />
      <img :src="pinterest" alt="Pinterest Icon" class="pinterest" />
    </div>
    <div class="share-icon" @click="toggleShareOff">
      <div class="pointer"></div>
      <img :src="shareWhite" alt="Share Icon" class="icon-white" />
    </div>
  </div>
  </transition>
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
.share-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: var(--very-dark-gray-blue);
  padding: 18px 32px;
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
  animation: jello-horizontal 0.9s both;
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

.pointer {
  display: none;
}

@keyframes jello-horizontal {
  0% {
    transform: scale3d(1, 1, 1);
  }
  30% {
    transform: scale3d(1.25, 0.75, 1);
  }
  40% {
    transform: scale3d(0.75, 1.25, 1);
  }
  50% {
    transform: scale3d(1.15, 0.85, 1);
  }
  65% {
    transform: scale3d(0.95, 1.05, 1);
  }
  75% {
    transform: scale3d(1.05, 0.95, 1);
  }
  100% {
    transform: scale3d(1, 1, 1);
  }
}

/* @media screen and (min-width: 600px) {
  .share-container {
    width: 248px;
    height: 67px;
    border-radius: 10px;
  }

  .share-icon {
    display: none;
  }
} */
</style>