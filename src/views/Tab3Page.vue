<template>
  <ion-page>
    <HeaderDefault title="Mapbox" />
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Mapbox</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content class="ion-padding">
        <ion-text>Mapbox is coming soon</ion-text>
      </ion-content>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import HeaderDefault from '@/components/elements/HeaderDefault.vue'
import {
  IonContent,
  IonHeader,
  IonPage,
  IonText,
  IonTitle,
  IonToolbar
} from '@ionic/vue'
</script>
