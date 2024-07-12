<template>
  <ion-item>
    <ButtonDefault
      id="calc-alert"
      :color="clickCounter > 0 ? 'danger' : 'light'"
      :disabled="clickCounter < 0"
      class="ion-padding"
      title="-"
      @click="clickCounter--"
    />
    <ButtonDefault
      :color="clickCounter >= 0 ? 'success' : 'light'"
      class="ion-padding"
      title="+"
      @click="clickCounter++"
    />
    <ion-badge slot="end" class="ion-padding">{{ clickCounter }}</ion-badge>
  </ion-item>
  <ion-alert
    v-if="clickCounter < 1"
    :buttons="alertButtons"
    header="Stop clicking"
    message="So I add +1 again"
    sub-header="Less than zero is not possible"
    trigger="calc-alert"
  ></ion-alert>
</template>

<script lang="ts" setup>
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
