<template>
  <ion-content>
    <StreamBarcodeReader
      @decode="(a, b, c) => onDecode(a, b, c)"
      @loaded="() => onLoaded()"
    ></StreamBarcodeReader>
    <ion-item :color="text ? 'success' : 'danger'">
      <span class="ion-margin-end">Input value:</span>
      <span>{{ text || 'Nothing' }}</span></ion-item
    >
    <ion-fab class="ion-margin-top" horizontal="end">
      <ion-fab-button @click="toggleFlashLight">
        <ion-icon :icon="torch ? flash : flashOutline"></ion-icon>
      </ion-fab-button>
    </ion-fab>
  </ion-content>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import { IonContent, IonFab, IonFabButton, IonIcon } from '@ionic/vue'
import { StreamBarcodeReader } from 'vue-barcode-reader'
import { flash, flashOutline } from 'ionicons/icons'

const text = ref('')
let id: any = null

const onDecode = (a: any, b: any, c: any) => {
  console.log(a, b, c)
  text.value = a
  if (id) clearTimeout(id)
  id = setTimeout(() => {
    if (text.value === a) {
      text.value = ''
    }
  }, 5000)
}

const onLoaded = () => {
  console.log('load')
}

const torch = ref(false)

const toggleFlashLight = () => {
  torch.value = !torch.value
}
</script>
