<template>
  <ion-page ref="page">
    <HeaderDefault title="Modal" />
    <ion-content class="ion-padding">
      <ion-button id="open-sheed-modal" class="center-button"
        >{{ title }}
      </ion-button>
      <ion-modal
        ref="modal"
        trigger="open-sheed-modal"
        :initial-breakpoint="0.25"
        :breakpoints="[0, 0.25, 0.5, 0.75]"
      >
        <HeaderModal title="Modal" />

        <ion-content class="ion-padding">
          <ion-range
            label-placement="start"
            label="Label at the Start"
          ></ion-range>

          <br />

          <ion-range label-placement="end" label="Label at the End"></ion-range>

          <br />

          <ion-range
            label-placement="fixed"
            label="Fixed Width Label"
          ></ion-range>

          <br />

          <ion-range
            label-placement="stacked"
            label="Stacked Label"
          ></ion-range>
        </ion-content>
      </ion-modal>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonButton, IonContent, IonModal, IonPage } from '@ionic/vue'
import HeaderDefault from './elements/HeaderDefault.vue'
import HeaderModal from './elements/HeaderModal.vue'

defineProps<{
  title: string
}>()
</script>

<style scoped>
.center-button {
  text-align: center;
  position: absolute;
  left: 25%;
  right: 25%;
  top: 50%;
  transform: translateY(-50%);
}
</style>
