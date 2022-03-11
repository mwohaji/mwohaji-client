<template>
  <form>
    <button :disabled="cardNumber <= 0">행동 생성하기</button>
    <div class="count">
      <input type="number" v-model="cardNumber" />
      <div>개 생성</div>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      cardNumber: 0,
    }
  },
}
</script>

<style scoped>
form {
  max-width: 400px;
  width: 100%;
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  gap: 20px;
}
button {
  max-width: 270px;
  width: 100%;
  height: 50px;
  border: none;
  border-radius: 10px;
  background-color: var(--light-gray-color);
  color: var(--font-color);
  cursor: pointer;
}

button:disabled,
button[disabled] {
  background-color: var(--nomal-gray-color);
  color: var(--border-color);
  cursor: not-allowed;
}
.count {
  display: flex;
  align-items: flex-end;
  width: 100px;
  white-space: nowrap;
}

input {
  width: 50px;
  text-align: center;
  border: none;
  outline: none;
  border-bottom: 1px solid var(--font-color);
  font-size: 20px;
  font-weight: bold;
  background-color: var(--background-color);
  color: var(--font-color);
}
</style>
