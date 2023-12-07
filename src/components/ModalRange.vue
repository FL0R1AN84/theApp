<template>
  <ion-page ref="page">
    <HeaderDefault title="Modal" />
    <ion-content class="ion-padding">
      <ion-button :id="trigger" class="container">{{ title }} </ion-button>
      <ion-modal
        ref="modal"
        :trigger="trigger"
        :initial-breakpoint="initialBreakpoint"
        :breakpoints="breakpoints"
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
import HeaderModal from './elements/HeaderModal.vue'

defineProps<{
  title: string
  trigger: string
  initialBreakpoint?: number
  breakpoints?: Array<number>
}>()
</script>

<style scoped></style>
