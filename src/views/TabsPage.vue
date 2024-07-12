<template>
  <ion-page>
    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar slot="bottom" translucent>
        <ion-tab-button href="/tabs/tab1" tab="tab1">
          <ion-icon :icon="contrastOutline" aria-hidden="true" />
          <ion-label>Mode</ion-label>
        </ion-tab-button>

        <ion-tab-button href="/tabs/tab2" tab="tab2">
          <ion-icon :icon="chevronExpandOutline" aria-hidden="true" />
          <ion-label>Modal</ion-label>
        </ion-tab-button>

        <ion-tab-button href="/tabs/tab3" tab="tab3">
          <ion-fab>
            <ion-fab-button :color="tabFocus ? 'primary' : 'dark'">
              <ion-icon
                :icon="navigateOutline"
                aria-hidden="true"
                color="light"
              />
            </ion-fab-button>
          </ion-fab>
        </ion-tab-button>

        <ion-tab-button href="/tabs/tab4" tab="tab4">
          <ion-icon :icon="calculatorOutline" aria-hidden="true" />
          <ion-label>Calc</ion-label>
        </ion-tab-button>

        <ion-tab-button id="open-scanner" href="/tabs/tab5" tab="tab5">
          <ion-icon :icon="qrCodeOutline" aria-hidden="true" />
          <ion-label>Scanner</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script lang="ts" setup>
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
</script>

<style lang="scss" scoped>
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
