<template>
  <ion-page>
    
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title> {{ greeting }} </ion-title>
        <ion-buttons slot="end">
          <ion-button router-link="/test" routerDirection="forward" color="dark">
            <ion-icon :icon="timeOutline" size="large" />
          </ion-button>
        </ion-buttons>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar class="tab-toolbar">
          <ion-title size="large"> {{ greeting }} </ion-title>
        </ion-toolbar>
      </ion-header>
    </ion-content>

  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonIcon, IonButton, IonButtons } from '@ionic/vue';
import { timeOutline } from 'ionicons/icons';

export default defineComponent({
  name: 'Home',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage, IonIcon, IonButton, IonButtons },
  setup() {
    return {
      timeOutline,
    }
  },
  data(): any {
    return {
      greeting: 'Hello'
    }
  },
  created() {
    const hours = new Date().getHours();
     
    if (hours > 18) {
      this.greeting = 'Good Evening';
    } else if (hours > 12) {
      this.greeting = 'Good Day';
    } else {
      this.greeting = 'Good Morning';
    }
  },
});
</script>
