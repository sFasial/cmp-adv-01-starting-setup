<template>
    <h2>Manage Goals</h2>

    <div>
        <label>Add Goal</label>
        <input type="text" placeholder="Add Goal" ref="saveInput">
        <button @click="SetGoal">Set Goal</button>
    </div>

  <teleport to="#app">
    <error-alert v-if="isInputInvalid" :isOpen="isInputInvalid" @close="isInputInvalid = false">
        <template v-slot:default>
            <h2>Input is Invalid</h2>
            <p>Please enter at least a few characters</p>
            <button @click="isInputInvalid = false">SetisInputInvalid</button>
        </template>
    </error-alert>
  </teleport>
</template>

<script>
// import ErrorAlert from './ErrorAlert.vue';

export default {
    // components: {
    //     ErrorAlert
    // },
    data() {
        return {
            isInputInvalid: false
        }
    },
    methods: {
        SetGoal() {
            console.log('saveInput Ref', this.$refs.saveInput.value);
            this.isInputInvalid = this.$refs.saveInput.value === '';
        }
    }
}
</script>
