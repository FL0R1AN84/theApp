<template>
  <ion-page>
    <HeaderDefault title="Scanner" />
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Scanner</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content class="ion-padding">
        <BarcodeScanner
          :breakpoints="[0, 1]"
          :initial-breakpoint="1"
          title="Scanner"
          trigger="open-scanner"
        />
      </ion-content>
    </ion-content>
  </ion-page>
</template>

<script lang="ts" setup>
import BarcodeScanner from '@/components/BarcodeScanner.vue'
import HeaderDefault from '@/components/elements/HeaderDefault.vue'
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar
} from '@ionic/vue'
</script>
