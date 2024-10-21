<template>
  <main class="max-w-2xl px-4 mx-auto">
    <nav
      class="mb-4 font-medium text-center text-gray-500 border-b border-gray-200"
    >
      <ul class="flex flex-wrap">
        <li v-for="tab in tabs" :key="tab.key">
          <TabLink :tab="tab" :currentTab="currentTab" />
        </li>
      </ul>
    </nav>
  </main>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import type { TabKey, Tab } from '@/types'

import TabLink from '@/components/TabLink.vue'

const tabs: Tab[] = [
  {
    key: 'General',
    label: 'General',
  },
  {
    key: 'Notifications',
    label: 'Notifications',
  },
  {
    key: 'Privacy',
    label: 'Privacy',
  },
]

const currentTab = ref<TabKey>('General')
</script>

<style scoped></style>
