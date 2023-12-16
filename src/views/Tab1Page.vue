<template class="dark">
  <ion-page>
    <HeaderDefault :title="isDark ? 'DarkMode' : 'LightMode'" />
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">{{
            isDark ? 'DarkMode' : 'LightMode'
          }}</ion-title>
        </ion-toolbar>
      </ion-header>
      <DarkMode v-if="isDark" @click="toggleDark()" />
      <LightMode v-if="!isDark" @click="toggleDark()" />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import DarkMode from '@/components/DarkMode.vue'
import LightMode from '@/components/LightMode.vue'
import HeaderDefault from '@/components/elements/HeaderDefault.vue'
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar
} from '@ionic/vue'
import { useDark, useToggle } from '@vueuse/core'

const isDark = useDark()
const toggleDark = useToggle(isDark)
</script>
