<template>
  <section class="header">
    <HeaderButton v-for="btn in btns" :key="btn.name" @click="() => emit('click', btn.action)">
      <component :is="btn.name" />
    </HeaderButton>
    <span @click="emit('click', 'copy')" class="header__copy"> copy HTML </span>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue';

import HeaderButton from '@/components/HeaderButton.vue';

import ArrowLeftIcon from '@/components/icons/ArrowLeftIcon.vue';
import ArrowRightIcon from '@/components/icons/ArrowRightIcon.vue';
import TitleIcon from '@/components/icons/TitleIcon.vue';
import SmallTextIcon from '@/components/icons/SmallTextIcon.vue';
import PictureIcon from '@/components/icons/PictureIcon.vue';

interface Btns {
  name: any;
  action: string;
}

const emit = defineEmits(['click']);

const btns = ref<Btns[]>([
  {
    name: ArrowLeftIcon,
    action: 'undo',
  },
  {
    name: ArrowRightIcon,
    action: 'redo',
  },
  {
    name: TitleIcon,
    action: 'heading',
  },
  {
    name: SmallTextIcon,
    action: 'insertParagraph',
  },
  {
    name: PictureIcon,
    action: 'insertImage',
  },
]);
</script>

<style lang="scss" scoped>
@import '@/assets/colors';
.header {
  height: 38px;
  display: flex;
  gap: 12px;
  &__copy {
    display: flex;
    align-items: center;
    color: $blue;
    cursor: pointer;
  }
}
</style>
