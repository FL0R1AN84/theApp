<template>
  <ion-header>
    <ion-toolbar>
      <ion-title>{{ title }}</ion-title>
      <ion-buttons slot="start">
        <ion-button @click="dismiss()">Close</ion-button>
      </ion-buttons>
    </ion-toolbar>
  </ion-header>
</template>

<script setup lang="ts">
import {
  IonButton,
  IonButtons,
  IonHeader,
  IonTitle,
  IonToolbar,
  modalController
} from '@ionic/vue'

defineProps<{
  title: string
}>()

const dismiss = () => {
  modalController.dismiss()
}
</script>
