<script setup lang="ts">
import { ref } from "vue"
import type { ButtonProps } from "./types"

defineOptions({
  name: 'YgButton'
})
const props = withDefaults(defineProps<ButtonProps>(), {
  tag: 'button',
  nativeType: 'button',
})
const slots = defineSlots()
const _ref = ref<HTMLButtonElement>()
</script>
<template>
  <component :is="props.tag" ref="_ref" :type="tag === 'button' ? nativeType : void 0"
    :disabled="disabled || loading ? true : void 0" :class="{
      [`yg-button--${type}`]: type,
      [`yg-button--${size}`]: size,
      'is-plain': plain,
      'is-round': round,
      'is-circle': circle,
      'is-disabled': disabled,
      'is-loading': loading,
    }">
    <slot></slot>
    </component>
</template>