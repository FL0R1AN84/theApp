<template>
  <ion-item>
    <ButtonDefault
      id="calc-alert"
      :color="clickCounter > 0 ? 'danger' : 'light'"
      :disabled="clickCounter < 0"
      title="-"
      @click="clickCounter--"
    />
    <ButtonDefault
      :color="clickCounter >= 0 ? 'success' : 'light'"
      title="+"
      @click="clickCounter++"
    />
    <ion-badge slot="end">{{ clickCounter }}</ion-badge>
  </ion-item>
  <ion-alert
    v-if="clickCounter < 1"
    trigger="calc-alert"
    header="Stop clicking"
    sub-header="Less than zero is not possible"
    message="So I add +1 again"
    :buttons="alertButtons"
  ></ion-alert>
</template>

<script setup lang="ts">
import { IonAlert, IonBadge, IonItem } from '@ionic/vue'
import { ref, watch } from 'vue'
import ButtonDefault from './elements/ButtonDefault.vue'

const clickCounter = ref(0)

watch(clickCounter, (newValue) => {
  setTimeout(() => {
    if (newValue === -1) {
      clickCounter.value += 1
    }
  }, 750)
})
const alertButtons = ['close']
</script>
