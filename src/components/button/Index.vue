<template>
  <button class="my-button" :class="buttonClass">
    <slot></slot>
  </button>
</template>

<script lang="ts">
import { defineComponent, computed } from 'vue';

export default defineComponent({
  name: 'MyButton',
  props: {
    type: {
      type: String,
      default: 'default',
    },
  },
  setup(props) {
    const buttonClass = computed(() => ({
      [`my-button--${props.type}`]: props.type,
    }));

    return {
      buttonClass,
    };
  },
});
</script>

<style lang="scss">
.my-button {
  // 按钮样式
}
</style>
