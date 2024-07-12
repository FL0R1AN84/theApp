<template>
  <ion-page>
    <HeaderDefault title="Calc" />
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Calc</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content class="ion-padding">
        <CalculateAlert />
      </ion-content>
    </ion-content>
  </ion-page>
</template>

<script lang="ts" setup>
import CalculateAlert from '@/components/CalculateAlert.vue'
import HeaderDefault from '@/components/elements/HeaderDefault.vue'
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar
} from '@ionic/vue'
</script>
