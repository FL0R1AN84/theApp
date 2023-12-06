<template>
  <ion-button> {{ title }} </ion-button>
</template>

<script setup lang="ts">
defineProps<{
  title: string
}>()
</script>
