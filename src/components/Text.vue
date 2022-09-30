<template>
  <div class="container">
    <h1 class="heading">
      Shift the overall look and feel by adding these wonderful touches to
      furniture in your home
    </h1>
    <p class="main-paragraph" ref="paragraph">
      Ever been in a room and felt like something was missing? Perhaps it felt
      slightly bare and uninviting. I’ve got some simple tips to help you make
      any room feel complete.
    </p>

    <div>
      <Author @open="toggleShare" />
    </div>

    <div>
      <Share @close="toggleShare" v-show="isShare" class="share-component"/>
    </div>
  </div>


</template>

<script>
import Author from "./Author.vue";
import Share from "./Share.vue";

export default {
  data() {
    return {
      isShare: false,
    };
  },

  components: { Author, Share },

  methods: {
    toggleShare() {
      this.isShare = !this.isShare;
    },
  },
};
</script>

<style>
.container {
  position: relative;
  width: 100%;
  padding: 36px 32px 20px 32px;
}

.heading {
  font-weight: 700;
  font-size: 16px;
  line-height: 24px;
  letter-spacing: 0.2px;
  color: var(--very-dark-gray-blue);
  margin-bottom: 12px;
}

.main-paragraph {
  line-height: 20px;
  letter-spacing: 0.13px;
  margin-bottom: 32px;
}

.share-component {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 2;
}

@media screen and (min-width: 600px) {
  .heading {
    font-size: 20px;
    letter-spacing: 0.25px;
    line-height: 28px;
  }

  .main-paragraph {
    margin-bottom: 20px;
  }

  .container {
    padding: 32px 40px;
  }

  .share-container {
    max-width: 248px;
    height: 55px;
    border-radius: 10px;
  }

  .share-component {
    bottom: 100px;
    margin: 0 auto;
  }
}

@media screen and (min-width: 660px) {
  .share-component {
    left: 50px;
    right: -20px;
  }
}

@media screen and (min-width: 760px) {
  .share-component {
    left: 120px;
    right: -50px;
  }
}

@media screen and (min-width: 810px) {
  .share-component {
    left: 150px;
    right: -80px;
  }
}

@media screen and (min-width: 920px) {
  .share-component {
    left: 200px;
    right: -80px;
  }
}
</style>