<template>
  <button class="header-btn">
    <slot />
  </button>
</template>

<style lang="scss" scoped>
@import '@/assets/colors';
.header-btn {
  background-color: $gray;
  border-width: 0;
  height: 38px;
  min-width: 42px;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  user-select: none;
  border-radius: 4px;
}
</style>
