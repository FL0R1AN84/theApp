<template>
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
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import HeaderDefault from '@/components/elements/HeaderDefault.vue'
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar
} from '@ionic/vue'
import { usePreferredDark } from '@vueuse/core'

const isDark = usePreferredDark()
</script>
