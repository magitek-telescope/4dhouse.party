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

    <ActiveMemberList :users="users.filter((u)=>u.active)" />

    <section class="main container">
      <div class="main-content">
        <div class="live">
          <iframe width="570" height="320" src="https://www.youtube.com/embed/4NLUHglR12o?rel=0" frameborder="0" allowfullscreen></iframe>
        </div>

        <h2 class="section-title">
          <span>宿泊スケジュール</span>
        </h2>

        <Schedule :users="users" />

      </div>
      <div class="sub-content">
        <h2 class="section-title">
          <span>Members</span>
        </h2>
        <Members :users="users" />
      </div>
    </section>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

import Members from '~/components/Members.vue'
import Schedule from '~/components/Schedule.vue'
import ActiveMemberList from '~/components/ActiveMemberList.vue'

export default {
  components: {
    Logo,
    Members,
    Schedule,
    ActiveMemberList
  },
  data () {
    return {
      users: [
        { name: 'potato4d', github: 'potato4d', active: true },
        { name: 'nametaketakewo', github: 'nametaketakewo', active: false },
        { name: 'lightnet328', github: 'lightnet328', active: true }
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

@media (max-width: 960px) {
  .main.container{
    width: 100%;
    flex-direction: column;
  }

  .main .main-content,
  .main .sub-content{
    width: 100%;
  }

  iframe{
    width: 100%;
    height: auto;
  }
}
</style>
