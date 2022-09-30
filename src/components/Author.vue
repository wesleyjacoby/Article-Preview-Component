<template>
  <div class="author-share">
    <div class="author">
      <img :src="avatar" alt="Profile Picture" class="avatar" />
      <div class="author-details">
        <p class="author-name">Michelle Appleton</p>
        <p class="author-date">28 Jun 2020</p>
      </div>
    </div>
    <div class="share-icon" @click="toggleShareOn" ref="share" defaultShare>
      <img :src="share" alt="Share Icon" class="icon" ref="image"/>
    </div>
  </div>
</template>

<script>
import avatar from "/src/assets/images/avatar-michelle.jpg";
import share from "/src/assets/images/icon-share.svg";
import shareWhite from "/src/assets/images/icon-share-white.svg";

export default {
  data() {
    return {
      avatar: avatar,
      share: share,
      shareWhite: shareWhite,
      defaultShare: true,
    };
  },
  methods: {
    toggleShareOn() {
      if(this.defaultShare === true) {
        this.$refs.share.style.backgroundColor = 'hsl(214, 17%, 51%)';
        this.$refs.image.src = shareWhite;
        this.defaultShare = false;
      } else {
        this.$refs.share.style.backgroundColor = 'hsl(210, 46%, 95%)';
        this.$refs.image.src = share;
        this.defaultShare = true;
      }
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
  width: 2.5rem;
  height: auto;
  margin-right: 1rem;
}

.author-details {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.author-name {
  font-weight: 700;
  line-height: 1.25rem;
  letter-spacing: 0.13px;
  color: var(--very-dark-gray-blue);
}

.author-date {
  line-height: 1.25rem;
  letter-spacing: 0.13px;
  color: var(--gray-blue);
}

.share-icon {
  display: inline-block;
  border-radius: 50%;
  background-color: var(--light-gray-blue);
  padding: 0.625rem;
}

.share-icon:hover {
  cursor: pointer;
}
</style>