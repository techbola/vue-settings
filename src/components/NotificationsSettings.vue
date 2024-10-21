<template>
  <div>
    <h2 class="mb-4 text-2xl">Notifications</h2>
    <form class="mx-auto space-y-4" @submit.prevent="save">
      <div class="flex items-center gap-1">
        <input type="checkbox" v-model="notifications.email" />
        <label>Email notifications</label>
      </div>
      <div class="flex items-center gap-1">
        <input type="checkbox" v-model="notifications.sms" />
        <label>SMS Notifications</label>
      </div>

      <button type="submit" class="btn-primary">Save</button>
    </form>
  </div>
</template>

<script setup lang="ts">
import { useSettings } from '@/composables/useSettings'
import { useNotifications } from '@/composables/useNotifications'

const { notifications } = useSettings()
const { addNotification } = useNotifications()

const save = () => {
  addNotification('General Settings saved!')
}
</script>
