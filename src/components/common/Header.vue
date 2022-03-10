<template>
  <div class="wrapper">
    <font-awesome-icon icon="trophy" class="fa-xl" />
    <font-awesome-icon icon="bars" class="fa-xl" @click="IS_OPEN_MENU(true)" />
  </div>
</template>

<script>
import { mapMutations } from 'vuex'
export default {
  methods: {
    ...mapMutations(['IS_OPEN_MENU']),
  },
}
</script>

<style scoped>
.wrapper {
  width: 100%;
  height: 70px;
  background-color: var(--header-color);
  display: flex;
  align-items: center;
  justify-content: right;
  padding: 10px;
}
.wrapper svg {
  margin: 10px;
  cursor: pointer;
}
</style>
