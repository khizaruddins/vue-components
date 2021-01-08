<template>
  <div>
    <h2>Manage Goals</h2>
    <input type="text" name="text" ref="goal" />
    <button @click="setGoal()">Set Goal</button>
    <teleport to="#app">
      <error-alert v-if="inputIsInvalid">
        <h2>Input is Invalid</h2>
        <p>Please Enter some input</p>
        <button @click="confirmError">Ok</button>
      </error-alert>
    </teleport>
  </div>
</template>

<script>
import ErrorAlert from "./ErrorAlert.vue";
export default {
  components: {
    ErrorAlert,
  },
  data() {
    return {
      inputIsInvalid: false,
    };
  },
  methods: {
    setGoal() {
      const enteredValue = this.$refs.goal.value;
      console.log(enteredValue);
      if (enteredValue === "") {
        this.inputIsInvalid = true;
      }
      console.log(enteredValue);
    },
    confirmError() {
      this.inputIsInvalid = false;
    },
  },
};
</script>
