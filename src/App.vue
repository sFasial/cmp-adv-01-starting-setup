<template>
  <div>
    <the-header></the-header>
    <badge-list></badge-list>
    <user-info :full-name="activeUser.name" :info-text="activeUser.description" :role="activeUser.role"></user-info>
    <KeepAlive>
      <manage-goals v-if="this.WhichComponentToDisplay == 'Manage'"></manage-goals>
      <active-goals v-else></active-goals>
    </KeepAlive>
    <button @click="SetGoal('Active')">Active Goal</button>
    <button @click="SetGoal('Manage')">Manage Goal</button>
  </div>
</template>

<script>

import TheHeader from './components/TheHeader.vue';
import BadgeList from './components/BadgeList.vue';
import UserInfo from './components/UserInfo.vue';
import ManageGoals from './components/ManageGoals.vue';
import ActiveGoals from './components/ActiveGoals.vue';
export default {
  components: {
    'the-header': TheHeader,
    BadgeList,
    UserInfo,
    ManageGoals,
    ActiveGoals
  },
  data() {
    return {
      WhichComponentToDisplay: '',
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods: {
    SetGoal(goal) {
      console.log('goal', goal);
      this.WhichComponentToDisplay = goal
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
</style>