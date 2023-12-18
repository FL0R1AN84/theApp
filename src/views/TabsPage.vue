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
          <ion-fab>
            <ion-fab-button>
              <ion-icon aria-hidden="true" :icon="chevronExpandOutline" />
            </ion-fab-button>
          </ion-fab>
        </ion-tab-button>

        <ion-tab-button tab="tab3" href="/tabs/tab3">
          <ion-icon aria-hidden="true" :icon="calculatorOutline" />
          <ion-label>Calc</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script setup lang="ts">
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
  contrastOutline
} from 'ionicons/icons'
</script>

<style scoped>
ion-tab-bar {
  height: 75px;
}
</style>
