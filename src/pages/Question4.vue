<template>
  <q-page class="questions-page">
    <p class="question-text">
      Find the smallest number from the given input
    </p>

    <p>
      Enters the numbers with comma separated.
    </p>

    <input v-model="inputValue" />

    <q-btn
      no-caps
      unelevated
      label="Run"
      color="primary"
      :disabled="!inputValue || !isValidInput"
      @click="findSmallestNumber"
      @keyup.enter="findSmallestNumber" />

    <p class="input-error" v-if="!isValidInput">
      Please input only numbers with comma seperated.
    </p>
  </q-page>
</template>

<script>
// vue
import { defineComponent, reactive, toRefs, computed } from "vue";

export default defineComponent({
  name: 'QuestionNumberFour',

  setup() {
    // state
    const state = reactive({
      inputValue: ''
    });

    const findSmallestNumber = () => {
      console.log(...(state.inputValue.split(',').map(number => +number)))
      const smallestNumber = Math.min(...(state.inputValue.split(',').map(number => +number)))
      console.log(smallestNumber)
      return smallestNumber
    }

    const isValidInput = computed(() => {
      return state.inputValue ? !/[a-zA-Z~!@#$%^&*()-[]{}\/?.<>|_+=]/.test(state.inputValue) && (/\d+,?/.test(state.inputValue)) : true
      if (state.inputValue) {
      }
      return false;
    })

    return {
      // state
      ...toRefs(state),
      findSmallestNumber,
      isValidInput
    }
  }
})
</script>

<style lang="scss" scoped></style>
