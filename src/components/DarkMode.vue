<template>
  <ion-content class="ion-padding" color="primary">
    <ion-button :color="isDark ? 'warning' : 'primary'" size="large">
      <ion-icon
        slot="icon-only"
        :icon="isDark ? sunnyOutline : moonOutline"
      ></ion-icon>
    </ion-button>
  </ion-content>
</template>

<script lang="ts" setup>
import { IonButton, IonContent, IonIcon } from '@ionic/vue'
import { useDark } from '@vueuse/core'
import { moonOutline, sunnyOutline } from 'ionicons/icons'

const isDark = useDark()
</script>
