<template>
  <!-- 全局化配置 ( 主题 ) -->
  <van-config-provider :theme="theme.dark ? 'dark' : 'light'">
    <router-view />
  </van-config-provider>
</template>

<script lang="ts" setup>
  import { settings } from '@/settings';

  const route = useRoute();
  const { t } = useI18n();

  const theme = useThemeStore();

  // 设置页面标题
  {
    const meta = route.meta || {};
    const titleTemplate = (meta.titleTemplate ?? settings.titleTemplate ?? `:title | ${settings.name}`) as string;

    useHead({
      title: titleTemplate.replaceAll(':title', t(`${meta.title ?? ''}`)),
    });
  }
</script>
