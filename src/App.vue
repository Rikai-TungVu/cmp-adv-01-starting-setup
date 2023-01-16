<template>
  <div>
    <the-header></the-header>
    <!-- <badge-list></badge-list>
    <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>
    <course-goals>
      <template #default="slotProps">
        <h2> {{ slotProps.item }} </h2>
        <p>{{ slotProps['another-props'] }}</p>
      </template>
    </course-goals> -->
    <button @click="setSelectedComponent('active-goals')">ActiveGoals</button>
    <button @click="setSelectedComponent('manager-goals')">ManagerGoals</button>
    <!-- <ManagerGoals v-if="selectedComponent == 'active-goals'"></ManagerGoals>
    <ActiveGoals v-if="selectedComponent == 'manager-goals'"></ActiveGoals> -->
    <component :is="selectedComponent"></component>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
/* khai báo TheHeader thành local componenent*/
/* import BadgeList from './components/BadgeList.vue'; */
/* import UserInfo from './components/UserInfo.vue'; */
/* Import trực tiếp vào component App*/
/* Thay vì khai báo hết ở main.js */
/* import CourseGoals from './components/CourseGoals.vue'; */
import ActiveGoals from './components/ActiveGoals.vue';
import ManagerGoals from './components/ManagerGoals.vue';

export default {
  components:{
    /* TheHeader: TheHeader, */
    /* TheHeader */
    'the-header': TheHeader,
    /* Định nghĩa component TheHeader */
    /* Local component name*/
    /* 'user-info': UserInfo, */
    /* 'badge-list': BadgeList, */
    /* 'course-goals': CourseGoals, */
    ActiveGoals,
    ManagerGoals
  },
  data() {
    return {
      selectedComponent:'active-goals',
      activeUser: {
        name: 'Manuel Fri',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods:{
    setSelectedComponent (cmp) {
      this.selectedComponent = cmp;
    }
  }
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
button {
  font: inherit;
  border: 1px solid #88005b;
  background-color: #88005b;
  color: white;
  padding: 1rem 2rem;
  border-radius: 12px;
  margin: 1rem;
  width: 12rem;
  cursor: pointer;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
</style>