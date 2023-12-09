<template>
  <ion-button>
    {{ title }}
  </ion-button>
</template>

<script setup lang="ts">
import { IonButton } from '@ionic/vue'

defineProps<{
  title: string
}>()
</script>
