<template lang="html">
  <ol>
    <li class="row">
      <dl>
        <dt class="row-head title">日付</dt>
        <dd class="row-head content">宿泊者</dd>
      </dl>
    </li>
    <li v-for="day in 5" class="row">
      <dl>
        <dt class="title">01/0{{day}}</dt>
        <dd class="content">
          <ul class="stay-users">
            <li v-for="user in users">
              <img :src="`https://github.com/${user.github}.png`" :alt="user.name" width="28">
            </li>
          </ul>
        </dd>
      </dl>
    </li>
  </ol>
</template>

<script>
export default {
  props: ['users']
}
</script>

<style scoped>

ol{
  display: block;
  margin: 0;
  padding: 0;
  list-style: none;
}

.row .row-head{
  font-weight: bold;
}

.title,
.content{
  color: #95989A;
  font-size: 14px;
}

.row,
.row dl{
  width: 100%;
  display: flex;
  align-items: stretch;
  justify-content: flex-start;
  height: 44px;
}

.row + .row {
  border-top: solid 1px #E0E0E0;
}

dl dt{
  width: 120px;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

dl dd{
  width: 120px;
  height: 100%;
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  padding: 0 15px;
}

dl dd .stay-users{
  display: flex;
  align-items: center;
  justify-content: flex-start;
  margin: 0;
  padding: 0;
  list-style: none;
}

dl dd .stay-users li{
  width: 28px;
  height: 28px;
  border-radius: 50%;
  overflow: hidden;
}

dl dd .stay-users li img{
  width: 100%;
  height: 100%;
  object-fit: cover;
}

dl dd .stay-users li + li{
  margin-left: 15px;
}
</style>
