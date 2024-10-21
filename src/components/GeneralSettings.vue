<template>
  <div>
    <h2 class="mb-4 text-2xl">General</h2>
    <form class="mx-auto space-y-4" @submit.prevent="save">
      <div>
        <label class="mb-1">Username</label>
        <input type="text" v-model="general.username" />
      </div>
      <div>
        <label class="mb-1">Email</label>
        <input type="email" v-model="general.email" />
      </div>
      <div>
        <label class="mb-1">About Me</label>
        <textarea v-model="general.about"></textarea>
      </div>
      <div>
        <label class="mb-1">Gender</label>
        <label>
          <input type="radio" value="male" v-model="general.gender" />
          <span>Male</span>
        </label>
        <label>
          <input type="radio" value="female" v-model="general.gender" />
          <span>Female</span>
        </label>
        <label>
          <input type="radio" value="other" v-model="general.gender" />
          <span>Other</span>
        </label>
      </div>
      <div>
        <label class="mb-1">Country</label>
        <select v-model="general.country">
          <option>USA</option>
          <option>Canada</option>
          <option>UK</option>
        </select>
      </div>
      <button type="submit" class="btn-primary">Save</button>
    </form>
  </div>
</template>

<script setup lang="ts">
import { useSettings } from '@/composables/useSettings'
import { useNotifications } from '@/composables/useNotifications'

const { general } = useSettings()
const { addNotification } = useNotifications()

const save = () => {
  addNotification('General Settings saved!')
}
</script>

<style lang="scss" scoped></style>
