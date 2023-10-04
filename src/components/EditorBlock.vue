<template>
  <section contenteditable class="editor-block" id="edit" />
</template>

<style lang="scss" scoped>
.editor-block {
  background-color: transparent;
  color: white;
  &:focus {
    outline-width: 0;
  }
}
</style>
