<template>
  <ion-page>
    <HeaderDefault title="Sheet" />
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Modal</ion-title>
        </ion-toolbar>
      </ion-header>

      <ModalRange
        title="Open as Sheet Modal"
        trigger="open-sheet-modal"
        :initial-breakpoint="0.25"
        :breakpoints="[0, 0.25, 0.5, 0.75]"
      />
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
