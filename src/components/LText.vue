<template>
  <div :style="styleStr" class="l-text__component">
    {{ text }}
    <slot />
  </div>
</template>

<script lang="ts" setup>
import { computed } from 'vue'
import { propsToStyleString } from '../defaultProps'

const props = defineProps<{
  text: string | undefined
  style: any
}>()

const styleStr = computed(() => {
  return propsToStyleString(props.style, false)
})
</script>

<style lang="scss">
button.l-text__component {
  padding: 5px 10px;
  cursor: pointer;
}

.l-text__component {
  box-sizing: border-box;
  white-space: pre-wrap;
}
</style>
