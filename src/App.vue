<template>
  <!-- 全局化配置 ( 主题 ) -->
  <van-config-provider :theme="theme.dark ? 'dark' : 'light'">
    <router-view />
  </van-config-provider>
</template>

<script lang="ts" setup>
  import { settings } from '@/settings';

  const theme = useThemeStore();

  useHead({
    title: settings.name,
  });
</script>
