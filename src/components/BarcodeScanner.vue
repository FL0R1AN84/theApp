<template>
  <ion-content>
    <StreamBarcodeReader
      @decode="(a, b, c) => onDecode(a, b, c)"
      @loaded="() => onLoaded()"
    ></StreamBarcodeReader>
    Input Value: {{ text || 'Nothing' }}
  </ion-content>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import { IonContent } from '@ionic/vue'
import { StreamBarcodeReader } from 'vue-barcode-reader'

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
</script>
