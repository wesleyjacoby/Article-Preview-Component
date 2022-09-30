<template>
  <div class="author-share">
    <div class="author">
      <img :src="avatar" alt="Profile Picture" class="avatar" />
      <div class="author-details">
        <p class="author-name">Michelle Appleton</p>
        <p class="author-date">28 Jun 2020</p>
      </div>
    </div>
    <div class="share-icon" @click="toggleShareOn">
      <img :src="share" alt="Share Icon" class="icon" />
    </div>
  </div>
</template>

<script>
import avatar from "/src/assets/images/avatar-michelle.jpg";
import share from "/src/assets/images/icon-share.svg";

export default {
  data() {
    return {
      avatar: avatar,
      share: share,
    };
  },
  methods: {
    toggleShareOn() {
      this.$emit("open");
    },
  },
};
</script>

<style>
.author-share {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.author {
  display: flex;
  justify-content: center;
  align-items: center;
}

.avatar {
  display: inline-block;
  border-radius: 50%;
  width: 40px;
  height: auto;
  margin-right: 16px;
}

.author-details {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.author-name {
  font-weight: 700;
  line-height: 20px;
  letter-spacing: 0.13px;
  color: var(--very-dark-gray-blue);
}

.author-date {
  line-height: 20px;
  letter-spacing: 0.13px;
  color: var(--gray-blue);
}

.share-icon {
  display: inline-block;
  border-radius: 50%;
  background-color: var(--light-gray-blue);
  padding: 10px;
}

.share-icon:hover {
  cursor: pointer;
}

/* @media screen and (min-width: 600px) {
  .author-share {
    padding: 0px;
  }
} */
</style>