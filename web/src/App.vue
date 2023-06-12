<template>
  <ConfigProvider :locale="getAntdLocale">
    <!-- 包装一个HTML标准模版，估计含有header和body -->
    <AppProvider>
      <!-- 执行展示页面 -->
      <RouterView />
      <!-- 路由规则 -->
    </AppProvider>
  
  </ConfigProvider>
</template>

<script lang="ts" setup>
  import { ConfigProvider } from 'ant-design-vue';
  import { AppProvider } from '/@/components/Application';
  import { useTitle } from '/@/hooks/web/useTitle';
  import { useLocale } from '/@/locales/useLocale';

  import 'dayjs/locale/zh-cn';
  // support Multi-language
  const { getAntdLocale } = useLocale();

  // Listening to page changes and dynamically changing site titles
  useTitle();
</script>
