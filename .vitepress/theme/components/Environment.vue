<script setup lang="ts">
import { defineProps } from 'vue'

defineProps<{ type: 'node' | 'client' }>()
</script>

<template>
  <details class="px-4 py-3 mt-4 rounded bg-gray-400 bg-opacity-10">
    <summary class="outline-none">
      环境：
      <span class="capitalize" :class="type === 'node' ? 'text-orange-400' : 'text-green-400'">{{ type }}</span>
    </summary>

    <div class="mt-2 opacity-75">
      <span v-if="type === 'node'">
        此配置仅在 Node.js 环境下运行。你可以访问 Node.js 的相关 API 了解更多。
      </span>
      <span v-else>
        此配置仅在客户端环境下运行。在引入包时，请确保浏览器的兼容性。
      </span>
    </div>
  </details>
</template>
