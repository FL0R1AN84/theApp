<template>
  <ion-page>
    <HeaderDefault title="Mapbox" />
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Mapbox</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content>
        <MapBox />
      </ion-content>
    </ion-content>
  </ion-page>
</template>

<script lang="ts" setup>
import HeaderDefault from '@/components/elements/HeaderDefault.vue'
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar
} from '@ionic/vue'
import MapBox from '@/components/MapBox.vue'
</script>
