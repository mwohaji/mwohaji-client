<template>
  <div class="wrapper">
    <div class="title">
      <router-link to="/">
        <font-awesome-icon icon="angle-left" class="fa-2x" />
      </router-link>
      <div class="title-text">로그인</div>
      <div class="title-text"></div>
    </div>
    <input class="input" placeholder="이메일" v-model="email" type="email" />
    <input
      class="input"
      placeholder="비밀번호"
      v-model="password"
      type="password"
    />
    <button class="btn">로그인</button>
  </div>
</template>

<script>
export default {
  setup() {
    let email = ''
    let password = ''

    return { email, password }
  },
}
</script>

<style scoped>
.wrapper {
  padding: 20px;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.title {
  width: 100%;
  display: flex;
  justify-content: space-between;
}

.title svg {
  cursor: pointer;
  color: var(--font-color);
}

.title-text {
  font-weight: bold;
  font-size: 24px;
}

.input {
  max-width: 900px;
  width: 100%;
  height: 50px;
  font-size: 16px;
  background-color: var(--light-btn-color);
  outline: none;
  border: none;
  border-bottom: 1px solid var(--dark-gray-color);
  color: var(--font-color);
  margin-top: 10px;
}
.input:focus {
  border-bottom: 1px solid var(--focus-color);
}
.btn {
  border: none;
  margin-top: 30px;
  background-color: var(--nomal-gray-color);
  color: var(--font-color);
  font-size: 16px;
  max-width: 900px;
  width: 100%;
  height: 50px;
  cursor: pointer;
}
</style>
