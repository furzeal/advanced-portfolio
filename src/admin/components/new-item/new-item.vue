<template lang="pug">
  .new-item-component
    button.button(
      type="button"
      :disabled="!isEnabled"
      @click="$emit('addNewItem')")
      Icon.button__icon(name="plus")
      .button__caption {{caption}}
</template>

<script>
import Icon from '../Icon.vue';

export default {
  data() {
    return {};
  },
  props: {
    caption: {
      type: String,
      default: '',
    },
    isEnabled: {
      type: Boolean,
      default: true,
    },
  },
  components: { Icon },
};
</script>

<style lang="postcss" scoped>
.new-item-component {
  height: 100%;
}
.button {
  height: 100%;
  width: 100%;
  background: $links-color;
  background: var(--bg-gradient);
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  transition: $delay;
  opacity: 0.99;

  &:hover {
    background: $links-color;
    background: var(--bg-reversed-gradient);
    opacity: 1;
  }

  & .button__icon {
    width: 150px;
    height: 150px;
    padding: 60px;
    border: 2px solid white;
    color: white;
    background: transparent;
    margin-bottom: 20px;
    overflow: hidden;
    border-radius: 50%;
  }
  & .button__caption {
    width: 60%;
    font-weight: 600;
    color: white;
    line-height: 30px;
  }

  // не вставлять сстили ниже disabled!
  &:disabled {
    cursor: default;
    background: $text-color30;
    &:hover {
      background: $text-color30;
    }
  }
}
</style>
