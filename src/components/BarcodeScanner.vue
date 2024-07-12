<template>
  <ion-modal
    ref="modal"
    :breakpoints="breakpoints"
    :initial-breakpoint="initialBreakpoint"
    :trigger="trigger"
  >
    <HeaderModal title="Scanner" />
    <QrcodeStream
      :paused="paused"
      @detect="onDetect"
      @error="onError"
      @camera-on="onCameraOn"
      @camera-off="onCameraOff"
    >
      <div v-show="showScanConfirmation" class="scan-confirmation">
        <ion-icon
          :icon="checkmarkCircleOutline"
          class="large-icon"
          color="success"
        ></ion-icon>
      </div>
    </QrcodeStream>
  </ion-modal>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import { QrcodeStream } from 'vue-qrcode-reader'
import { IonIcon, IonModal, toastController } from '@ionic/vue'
import { checkmarkCircleOutline } from 'ionicons/icons'
import HeaderModal from '@/components/elements/HeaderModal.vue'

defineProps<{
  breakpoints: Array<number>
  initialBreakpoint: number
  eventId?: number
  securityCode?: string
  ticketId?: number
  title: string
  trigger: string
}>()

const paused = ref(false)
const result = ref('')
const showScanConfirmation = ref(false)

const onCameraOn = () => {
  showScanConfirmation.value = false
}

const onCameraOff = () => {
  showScanConfirmation.value = true
}

const onDetect = async (detectedCodes: any[]) => {
  result.value = JSON.stringify(detectedCodes.map((code) => code.rawValue))
  paused.value = true
  await timeout(1000)
  paused.value = false
  await presentToast(result.value)
}

const timeout = (ms: number) => {
  return new Promise((resolve) => setTimeout(resolve, ms))
}

const presentToast = async (message: string) => {
  const toast = await toastController.create({
    message: message,
    duration: 2500,
    position: 'top',
    color: 'success'
  })
  await toast.present()
}

const presentErrorToast = async (message: string) => {
  const toast = await toastController.create({
    message: message,
    duration: 2500,
    position: 'top',
    color: 'danger'
  })
  await toast.present()
}

const onError = async (error: Error) => {
  console.error(error)
  await presentErrorToast(error.message)
}
</script>

<style scoped>
.scan-confirmation {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: rgba(255, 255, 255, 0.8);
  display: flex;
  flex-flow: row nowrap;
  justify-content: center;
  align-items: center;
}

.large-icon {
  font-size: 10rem;
  color: var(--ion-color-success);
}
</style>
