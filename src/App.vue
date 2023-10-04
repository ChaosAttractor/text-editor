<template>
  <section class="editor">
    <HeaderEditor @click="action" />
    <EditorBlock />
  </section>
</template>

<script setup lang="ts">
import HeaderEditor from './components/HeaderEditor.vue';
import EditorBlock from './components/EditorBlock.vue';

/**
 * casual func editor
 * P.S. execCommand depricated and will not appear on browsers soon
 * @param e - emitted event
 */
const action = (e: any) => {
  let val = '.header1';
  if (e === 'insertImage') {
    val = prompt('img link') || '';
  }
  document.execCommand(e, true, val);
};
</script>

<style lang="scss" scoped>
@import '@/assets/colors';

.editor {
  width: 80%;
  height: 300px;
  margin: 77px auto;
  display: flex;
  flex-direction: column;
  gap: 31px;
}
</style>
