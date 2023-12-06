<template>
  <ion-page>
    <HeaderDefault title="Sheet" />
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Modal</ion-title>
        </ion-toolbar>
      </ion-header>

      <ModalSheet title="Open as Modal" />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import ModalSheet from '@/components/ModalSheet.vue'
import HeaderDefault from '@/components/elements/HeaderDefault.vue'
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar
} from '@ionic/vue'
</script>
