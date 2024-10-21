<template>
  <div>
    <h2 class="mb-4 text-2xl">Privacy</h2>
    <form class="mx-auto space-y-4">
      <div class="flex items-center gap-1">
        <input type="checkbox" v-model="privacy.searchEngineIndexing" />
        <label>Search engine indexing</label>
      </div>

      <div>
        <label class="mb-1">Visibility</label>
        <select v-model="privacy.visibility">
          <option value="private">Private</option>
          <option value="public">Public</option>
        </select>
      </div>

      <button type="submit" class="btn-primary">Save</button>
    </form>
  </div>
</template>

<script setup lang="ts">
import { useSettings } from '@/composables/useSettings'

const { privacy } = useSettings()
</script>
