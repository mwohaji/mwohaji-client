<template>
  <div class="setting-list">
    <div class="setting-container" @click="isOpenTheme = !isOpenTheme">
      <div>테마</div>
      <div>시스템</div>
    </div>
    <transition name="theme">
      <form v-if="isOpenTheme" @change="changeTheme" class="theme-list">
        <label class="theme-container" for="system">
          <div>시스템</div>
          <input
            type="radio"
            id="system"
            name="theme"
            value="system"
            v-model="theme"
          />
        </label>
        <label class="theme-container" for="light">
          <div>라이트</div>
          <input
            type="radio"
            id="light"
            name="theme"
            value="light"
            v-model="theme"
          />
        </label>
        <label class="theme-container" for="dark">
          <div>다크</div>
          <input
            type="radio"
            id="dark"
            name="theme"
            value="dark"
            v-model="theme"
          />
        </label>
      </form>
    </transition>
    <div class="setting-container">비밀번호 변경</div>
    <div class="setting-container">로그아웃</div>
    <div class="setting-container">계정삭제</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpenTheme: false,
      theme: localStorage.getItem('color-theme'),
    }
  },
  methods: {
    changeTheme(e) {
      localStorage.setItem('color-theme', e.target.value)
      if (e.target.value === 'system') {
        const isOsColorTheme = window.matchMedia('(prefers-color-scheme: dark)')
          .matches
          ? 'dark'
          : 'light'
        document.documentElement.setAttribute('color-theme', isOsColorTheme)
      } else {
        document.documentElement.setAttribute('color-theme', e.target.value)
      }
    },
  },
}
</script>

<style scoped>
.theme-enter-from,
.theme-leave-to {
  transform: scaleY(0.7);
  opacity: 0;
}

.theme-enter-to,
.theme-leave-from {
  opacity: 1;
  transform: scaleY(1);
}

.theme-enter-active,
.theme-leave-active {
  transition: all 0.3s ease-out;
  transform-origin: top center;
}

.setting-list {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 30px;
}
.setting-container {
  width: 100%;
  font-size: 16px;
  border-bottom: 1px solid var(--nomal-gray-color);
  padding: 15px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.setting-container:nth-last-child(1) {
  color: #cb404e;
}
.theme-list {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.theme-container {
  padding: 10px 15px;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  cursor: pointer;
}
</style>
