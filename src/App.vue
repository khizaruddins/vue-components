<template>
  <div>
    <the-header></the-header>
    <button @click="setComponentSelected('active-goals')">Active Goal</button>
    <button @click="setComponentSelected('manage-goals')">Manage Goals</button>
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from "./components/layout/TheHeader.vue";
// import BaseCard from "./components/BaseCard.vue";
// import BaseBadge from "./components/BaseBadge.vue";
// import BadgeList from "./components/BadgeList.vue";
// import CourseGoal from "./components/CourseGoal.vue";
// import UserInfo from "./components/UserInfo.vue";
import ManageGoals from "./components/ManageGoals.vue";
import ActiveGoals from "./components/ActiveGoals.vue";

export default {
  components: {
    TheHeader,
    //BadgeList,
    //BaseBadge,
    //BaseCard,
    //UserInfo,
    //CourseGoal,
    ActiveGoals,
    ManageGoals,
  },
  data() {
    return {
      selectedComponent: "active-goals",
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin",
      },
    };
  },
  methods: {
    setComponentSelected(componentName) {
      this.selectedComponent = componentName;
    },
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
