<template lang="html">
  <ul class="members-list">
    <li v-for="user in users.filter((u)=>u.active)" class="member active">
      <img :src="`https://github.com/${user.github}.png`" :alt="user.name" width="40">
      <span>{{user.name}}</span>
    </li>
    <li v-for="user in users.filter((u)=>!u.active)" class="member inactive">
      <img :src="`https://github.com/${user.github}.png`" :alt="user.name" width="40">
      <span>{{user.name}}</span>
    </li>
  </ul>
</template>

<style scoped>
.members-list{
  margin: 15px 0 0;
  padding: 0;
  list-style: none;
}

.members-list .member{
  width: 100%;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  font-size: 16px;
  color: #666;
  font-weight: bold;
  position: relative;
}

.members-list .member img{
  border-radius: 50%;
  overflow: hidden;
  margin-right: 15px;
}

.members-list .member.inactive img {
  filter: grayscale(0);
}

.members-list .member + .member{
  margin-top: 15px;
}

.member::after{
  content: "";
  display: block;
  position: absolute;
  right: 0;
  top: calc(50% - 4px);
  width: 8px;
  height: 8px;
  border-radius: 50%;
}

.active::after{
  background: #00C308;
}

.inactive::after{
  background: #B37D7F;
}

</style>

<script>
export default {
  props: ['users']
}
</script>
