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
  padding: 2.25rem 2rem 1.25rem 2rem;
}

.heading {
  font-weight: 700;
  font-size: 1rem;
  line-height: 1.5rem;
  letter-spacing: 0.2px;
  color: var(--very-dark-gray-blue);
  margin-bottom: 0.75rem;
}

.main-paragraph {
  line-height: 1.25rem;
  letter-spacing: 0.13px;
  margin-bottom: 2rem;
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
    font-size: 1.25rem;
    letter-spacing: 0.25px;
    line-height: 1.75rem;
  }

  .main-paragraph {
    margin-bottom: 1.25rem;
  }

  .container {
    padding: 2rem 2.5rem;
  }

  .share-container {
    max-width: 15.5rem;
    height: 3.4375rem;
    border-radius: 0.625rem;
  }

  .share-component {
    bottom: 6.25rem;
    margin: 0 auto;
  }
}

@media screen and (min-width: 660px) {
  .share-component {
    left: 3.125rem;
    right: -1.25rem;
  }
}

@media screen and (min-width: 760px) {
  .share-component {
    left: 7.5rem;
    right: -3.125rem;
  }
}

@media screen and (min-width: 810px) {
  .share-component {
    left: 9.375rem;
    right: -5rem;
  }
}

@media screen and (min-width: 920px) {
  .share-component {
    left: 12.5rem;
    right: -5rem;
  }
}
</style>