<template>
  <Header />
  <Menu />
  <!-- <word-card></word-card> -->
</template>

<script>
import Header from '../components/common/Header.vue'
import Menu from '../components/Menu.vue'
import WordCard from '../components/WordCard.vue'
export default {
  components: { WordCard, Header, Menu },
}
</script>

<style scoped></style>
