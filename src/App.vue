<template>
  <div>
    <div class="my-profile">My profile</div>
    <ul class="dashboard">
      <li>
        <changing-avatar />
      </li>
      <li>
        <personal-info  />
      </li>
      <li>
        <changing-password />
      </li>
    </ul>
  </div>
</template>

<script>
import ChangingAvatar from '@/components/pages/ChangingAvatar'
import ChangingPassword from '@/components/pages/ChangingPassword'
import PersonalInfo from '@/components/pages/PersonalInfo'

export default {
  name: 'App',
  components: {
    ChangingAvatar, ChangingPassword, PersonalInfo
  }
}
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
  box-sizing: border-box;
}

.dashboard {
  display: flex;
  justify-content: space-between;
}

.my-profile{
  background: palevioletred;
  text-align: center;
  border-radius: 10px;
  box-shadow: 10px 5px 5px black;
  margin-bottom: 10px;
  color: white;
  font-size: 30px;
  font-family: 'Lato', sans-serif;
  font-family: 'Rubik Mono One', sans-serif;
}

.dashboard {
  list-style-type: none;
  padding-left: 20px;
  padding-right: 20px;
}
</style>
