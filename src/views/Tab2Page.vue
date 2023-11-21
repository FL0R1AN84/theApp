<template>
  <ion-page>
    <HeaderDefault title="Modal" />
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Modal</ion-title>
        </ion-toolbar>
      </ion-header>

      <ExploreContainer name="Open as Modal" />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent
} from '@ionic/vue'
import ExploreContainer from '@/components/ExploreContainer.vue'
import HeaderDefault from '@/components/elements/HeaderDefault.vue'
</script>
