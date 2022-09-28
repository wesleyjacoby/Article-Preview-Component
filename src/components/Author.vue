<template>
  <div class="author-share" v-show="isShare">
    <div class="author">
      <img :src="avatar" alt="Profile Picture" class="avatar" />
      <div class="author-details">
        <p class="author-name">Michelle Appleton</p>
        <p class="author-date">28 Jun 2020</p>
      </div>
    </div>
    <div class="share-icon" @click="toggleShare">
      <img :src="share" alt="Share Icon" class="icon" />
    </div>
  </div>

  <div v-show="!isShare">
    <Share @close="toggleShare" />
  </div>
</template>

<script>
import avatar from "/src/assets/images/avatar-michelle.jpg";
import share from "/src/assets/images/icon-share.svg";
import Share from "./Share.vue";

export default {
  components: { Share },
  data() {
    return {
      avatar: avatar,
      share: share,
      isShare: true,
    };
  },
  methods: {
    toggleShare() {
      this.isShare = !this.isShare;
    },
  },
};
</script>

<style>
.author-share {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 32px 20px 32px;
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
</style>