<template>
  <aside class="canvas-area" id="canvas-area">
    <EditBox v-for="com in componentList" :key="com.id" :comId="com.id" :defaultStyle="com.props">
      <LText :style="com.props" :text="com.text" />
    </EditBox>
  </aside>
</template>
<script lang="ts" setup>
import { computed } from 'vue'
import useEditorStore from '@/stores/editor'
import LText from '@/components/LText.vue'
import EditBox from '@/components/Editor/EditBox.vue'

const store = useEditorStore()
const componentList = computed(() => store.components)
console.log(
  '%c 🍨 componentList: ',
  'font-size:20px;background-color: #2EAFB0;color:#fff;',
  componentList
)
</script>
<style lang="scss" scoped>
.canvas-area {
  width: 335px;
  min-height: 600px;
  border: 1px solid #efefef;
  background: #fff;
  max-height: 80vh;
  position: relative;
}

.editor-wrapper {
  padding: 0px;
  cursor: pointer;
  border: 1px solid transparent;
  user-select: none;

  &:hover {
    border: 1px dashed #ccc;
  }
}
</style>
