<template>
  <div>
    <the-header></the-header>
    <badge-list></badge-list>
    <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import BadgeList from './components/BadgeList.vue';
import UserInfo from './components/UserInfo.vue';
/* Import trực tiếp vào component App*/
/* Thay vì khai báo hết ở main.js */


export default {
  components:{
    'the-header': TheHeader,
    /* Định nghĩa component TheHeader */
    /* Local component */
    'user-info': UserInfo,
    'badge-list': BadgeList
  },
  data() {
    return {
      activeUser: {
        name: 'Manuel Fri',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>