<template>
  <ion-page ref="page">
    <ion-header>
      <ion-toolbar>
        <ion-title>App</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <ion-button id="open-modal" class="center-button">{{ title }}</ion-button>

      <ion-modal
        ref="modal"
        trigger="open-modal"
        :presenting-element="presentingElement"
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
import {
  IonButtons,
  IonButton,
  IonModal,
  IonHeader,
  IonContent,
  IonToolbar,
  IonTitle,
  IonPage,
  modalController
} from '@ionic/vue'
import HeaderModal from './elements/HeaderModal.vue'

defineProps<{
  title: string
}>()

const presentingElement = null

const dismiss = () => {
  modalController.dismiss()
}
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
