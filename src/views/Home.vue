<template>
  <div class="wrapper">
    <div class="text_box">
      <div style="display: flex">
        <div class="text"></div>
        <span class="blink">|</span>
      </div>
      <div class="sub-text">할 일을 뽑고, 실행하세요</div>
    </div>

    <div class="btn-box">
      <router-link to="/register" class="home-btn">회원가입</router-link>
      <router-link to="/login" class="home-btn">로그인</router-link>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    const content = '뭐하지?'
    const text = document.querySelector('.text')
    const blink = document.querySelector('.blink')
    const subText = document.querySelector('.sub-text')
    let index = 0
    let interval = setInterval(typing, 500)

    function typing() {
      text.textContent += content[index++]
      if (index === content.length) {
        clearInterval(interval)
        blink.remove()
        subText.classList.add('text-fade')
      }
    }
  },
}
</script>

<style scoped>
.wrapper {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
}
.text_box {
  font-size: 2rem;
  font-weight: bold;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.blink {
  animation: blink 0.5s infinite;
  font-size: 2rem;
}

@keyframes blink {
  to {
    opacity: 0;
  }
}

.sub-text {
  opacity: 0;
  font-size: 16px;
}

.text-fade {
  animation: fadeIn 0.7s forwards;
  font-size: 16px;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    margin: 10px;
  }
  to {
    opacity: 1;
    margin: 0px;
  }
}

.btn-box {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
}
.home-btn {
  text-decoration: none;
  max-width: 900px;
  width: 100%;
  height: 50px;
  background-color: var(--light-gray-color);
  color: var(--text-color);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  margin-bottom: 25px;
}
</style>
