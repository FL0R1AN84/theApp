<template>
  <ion-page>
    <HeaderDefault title="Card" />
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Card</ion-title>
        </ion-toolbar>
      </ion-header>

      <ModalRange title="Open as Card Modal" trigger="open-card-modal" />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import ModalRange from '@/components/ModalRange.vue'
import HeaderDefault from '@/components/elements/HeaderDefault.vue'
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar
} from '@ionic/vue'
</script>
