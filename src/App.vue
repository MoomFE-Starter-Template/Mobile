<template>
  <!-- 全局化配置 ( 主题 ) -->
  <van-config-provider :theme="theme.dark ? 'dark' : 'light'">
    <router-view />
  </van-config-provider>
</template>

<script lang="ts" setup>
  const theme = useThemeStore();
</script>
