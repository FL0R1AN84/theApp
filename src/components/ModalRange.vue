<template>
  <ButtonDefault :id="trigger" :title="title" />
  <ion-modal
    ref="modal"
    :trigger="trigger"
    :initial-breakpoint="initialBreakpoint"
    :breakpoints="breakpoints"
  >
    <HeaderModal title="Modal" />

    <ion-content class="ion-padding">
      <ion-range label-placement="start" label="Label at the Start"></ion-range>

      <br />

      <ion-range label-placement="end" label="Label at the End"></ion-range>

      <br />

      <ion-range label-placement="fixed" label="Fixed Width Label"></ion-range>

      <br />

      <ion-range label-placement="stacked" label="Stacked Label"></ion-range>
    </ion-content>
  </ion-modal>
</template>

<script setup lang="ts">
import { IonContent, IonModal, IonRange } from '@ionic/vue'
import ButtonDefault from './elements/ButtonDefault.vue'
import HeaderModal from './elements/HeaderModal.vue'

defineProps<{
  title: string
  trigger: string
  initialBreakpoint?: number
  breakpoints?: Array<number>
}>()
</script>
