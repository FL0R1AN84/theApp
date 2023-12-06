<template>
  <ion-page>
    <HeaderDefault title="Card" />
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Modal</ion-title>
        </ion-toolbar>
      </ion-header>

      <ModalCard title="Open as Modal" />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import ModalCard from '@/components/ModalCard.vue'
import HeaderDefault from '@/components/elements/HeaderDefault.vue'
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar
} from '@ionic/vue'
</script>
