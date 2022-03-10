<template>
  <div class="profile-wrapper">
    <img class="profile-img" alt="" />
    <div>
      <div class="name">한준호</div>
      <div class="email">cloudtubekr@naver.com</div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.profile-wrapper {
  display: flex;
  align-items: center;
}
.profile-img {
  width: 45px;
  height: 45px;
  border-radius: 50%;
  margin-right: 10px;
}
.name {
  font-size: 20px;
  font-weight: bold;
}
.email {
  font-size: 16px;
  width: 180px;
  display: block;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow: hidden;
}
</style>
