<template>
  <ion-page>
    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar slot="bottom" translucent>
        <ion-tab-button tab="tab1" href="/tabs/tab1">
          <ion-icon aria-hidden="true" :icon="contrastOutline" />
          <ion-label>Mode</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="tab2" href="/tabs/tab2">
          <ion-icon aria-hidden="true" :icon="chevronExpandOutline" />
          <ion-label>Modal</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="tab3" href="/tabs/tab3">
          <ion-fab>
            <ion-fab-button :color="tabFocus ? 'primary' : 'dark'">
              <ion-icon
                aria-hidden="true"
                :icon="navigateOutline"
                color="light"
              />
            </ion-fab-button>
          </ion-fab>
        </ion-tab-button>

        <ion-tab-button tab="tab4" href="/tabs/tab4">
          <ion-icon aria-hidden="true" :icon="calculatorOutline" />
          <ion-label>Calc</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="tab5" href="/tabs/tab5">
          <ion-icon aria-hidden="true" :icon="qrCodeOutline" />
          <ion-label>Scanner</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script setup lang="ts">
import router from '@/router'
import {
  IonFab,
  IonFabButton,
  IonIcon,
  IonLabel,
  IonPage,
  IonRouterOutlet,
  IonTabBar,
  IonTabButton,
  IonTabs
} from '@ionic/vue'
import {
  calculatorOutline,
  chevronExpandOutline,
  contrastOutline,
  navigateOutline,
  qrCodeOutline
} from 'ionicons/icons'
import { computed } from 'vue'

const tabFocus = computed(() => {
  return router.currentRoute.value.path === '/tabs/tab3'
})

console.log('tabFocus :', tabFocus)
</script>

<style scoped lang="scss">
ion-tab-bar {
  height: 75px;
}

ion-fab-button {
  --background: var(--ion-color-dark);
  transition: transform 0.2s ease-in-out;

  &:active {
    transform: scale(0.95);
  }
}
</style>
