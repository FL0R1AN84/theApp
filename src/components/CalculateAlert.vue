<template>
  <HeaderDefault title="Calc" />
  <ion-item>
    <ButtonDefault title="Calculate and Alert" @click="clickCounter++" />
    <ion-badge slot="end">{{ clickCounter }}</ion-badge>
  </ion-item>
</template>

<script setup lang="ts">
import { IonBadge } from '@ionic/vue'
import { ref } from 'vue'
import ButtonDefault from './elements/ButtonDefault.vue'

const clickCounter = ref(0)
</script>
