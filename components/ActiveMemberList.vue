<template lang="html">
  <div class="userlist-wrapper">
    <div class="userlist container">
      <span class="title">今日の #4dhouse には {{users.length}} 人が滞在しています</span>
      <ul>
        <li v-for="user in users"><img :src="`https://github.com/${user.github}.png`" :alt="user.name"></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: ['users']
}
</script>

<style scoped>
.userlist-wrapper {
  width: 100%;
  height: 100px;
  color: #FFFFFF;
  font-size: 16px;
  background: #444449;
  line-height: 0;
}

.userlist .title{
  display: block;
  font-weight: bold;
  line-height: 1.0;
  padding: 15px;
}

.userlist{
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  height: 100%;
}

.userlist ul {
  padding: 0;
  margin: 0;
  list-style: none;
  display: flex;
  align-items: center;
  justify-content: center;
}

.userlist ul li {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  overflow: hidden;
}

.userlist ul li img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.userlist ul li + li{
  margin-left: 15px;
}
</style>
