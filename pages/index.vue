<template>
  <div class="">
    <header>
      <div class="spacing"></div>
      <h1>4dhouse.party</h1>
      <div class="userinfo">
        <div class="icon-wrap">
          <img class="icon" src="https://github.com/potato4d.png" alt="icon">
        </div>
        <span>potato4d</span>
      </div>
    </header>

    <UserList :users="activeUsers" />

    <section class="main container">
      <div class="main-content">
        <div class="live">
          <iframe width="570" height="320" src="https://www.youtube.com/embed/4NLUHglR12o?rel=0" frameborder="0" allowfullscreen></iframe>
        </div>

        <h2 class="section-title">
          <span>宿泊スケジュール</span>
        </h2>

      </div>
      <div class="sub-content">
        <h2 class="section-title">
          <span>Members</span>
        </h2>
        <ul class="members-list">
          <li v-for="user in users" class="member">
            <img :src="`https://github.com/${user.github}.png`" alt="potato4d" width="40">
            <span>{{user.name}}</span>
          </li>
        </ul>
      </div>
    </section>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import UserList from '~/components/UserList.vue'

export default {
  components: {
    Logo,
    UserList
  },
  data () {
    return {
      activeUsers: [
        { name: 'potato4d', github: 'potato4d' },
        { name: 'potato4d', github: 'potato4d' },
        { name: 'potato4d', github: 'potato4d' }
      ],
      users: [
        { name: 'potato4d', github: 'potato4d' },
        { name: 'potato4d', github: 'potato4d' },
        { name: 'potato4d', github: 'potato4d' },
        { name: 'potato4d', github: 'potato4d' },
        { name: 'potato4d', github: 'potato4d' }
      ]
    }
  }
}
</script>

<style media="screen">
.section-title{
  color: #95989A;
  font-size: 20px;
  font-weight: 300;
  padding: 0 0 15px;
  border-bottom: solid 2px #FF9D00;
}
</style>

<style scoped>
header{
  width: 100vw;
  height: 45px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: #FF9D00;
}

header h1{
  color: #fff;
  font-size: 20px;
  font-family: Chalkboard;
  height: 45px;
  display: flex;
  align-items: center;
  justify-content: center;
}

header .spacing{
  width: 140px;
}

header .userinfo{
  padding: 10px;
  width: 140px;
  height: 45px;
  color: #FF9D00;
  font-size: 14px;
  font-weight: bold;
  background: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}

header .userinfo .icon-wrap{
  width: 28px;
  height: 28px;
  border-radius: 50%;
  overflow: hidden;
  margin-right: 10px;
}

header .userinfo .icon{
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.main {
  min-height: calc(100vh - 185px);
  display: flex;
  align-items: stretch;
}

.main .main-content{
  width: 610px;
  padding: 20px;
  background: #fff;
}

.main .main-content .live{
  margin-bottom: 20px;
}

.main .sub-content{
  width: 340px;
  padding: 20px;
  background: #F8F8FA;
}

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
}

.members-list .member img{
  border-radius: 50%;
  overflow: hidden;
  margin-right: 15px;
}

.members-list .member + .member{
  margin-top: 15px;
}
</style>
