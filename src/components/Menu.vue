<template>
  <transition name="slide-background" tag="div">
    <div v-if="isOpenMenu">
      <div class="menu-wrapper" @click="IS_OPEN_MENU(false)" />
    </div>
  </transition>
  <transition name="slide" tag="div" class="menu">
    <div v-if="isOpenMenu">
      <Profile />
      <div class="follower-folloing">
        <div>3 팔로잉</div>
        <div>3 팔로워</div>
      </div>
      <SettingList />
    </div>
  </transition>
</template>

<script>
import { mapMutations, mapState } from 'vuex'
import Profile from './common/Profile.vue'
import SettingList from './SettingList.vue'

export default {
  components: { Profile, SettingList },
  computed: {
    ...mapState(['isOpenMenu']),
  },
  methods: {
    ...mapMutations(['IS_OPEN_MENU']),
  },
}
</script>

<style scoped>
.slide-enter-active,
.slide-leave-active {
  transition: transform 0.5s ease;
}

.slide-enter-from,
.slide-leave-to {
  transform: translateX(100%);
  transition: all 0.5s ease-in 0s;
  opacity: 0;
}

.slide-background-enter-from,
.slide-background-leave-to {
  transition: all 0.6s ease-in 0s;
  opacity: 0;
}

.menu-wrapper {
  background-color: rgba(0, 0, 0, 0.5);
  width: 100vw;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1;
}

.menu {
  padding: 20px;
  width: 300px;
  height: 100vh;
  background-color: var(--side-bar-color) !important;
  box-sizing: border-box;
  position: absolute;
  left: calc(100vw - 300px);
  top: 0;
  z-index: 2;
}

.follower-folloing {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-around;
  font-weight: bold;
  margin-top: 20px;
}

.setting-list {
  display: flex;
  flex-direction: column;
  justify-content: left;
}
</style>
