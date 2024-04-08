<template>
  <input :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" />
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: 'InputBox',
  props: {
    modelValue: {
      type: String,
    }
  },
})
</script>

<style lang="scss" scoped></style>
