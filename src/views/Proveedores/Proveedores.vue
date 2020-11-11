<template>
  <ion-split-pane content-id="main">
    <!--  the side menu  -->
    <ion-menu content-id="main">
      <ion-header>
        <ion-toolbar>
          <ion-title>Menu</ion-title>
        </ion-toolbar>
      </ion-header>
    </ion-menu>

    <!-- the main content -->
    <ion-router-outlet id="main"></ion-router-outlet>
  </ion-split-pane>
  <ion-content>
    <ion-card>
      <ion-card-header>
        <ion-card-subtitle>Proveedores</ion-card-subtitle>
        <ion-card-title>Card Title</ion-card-title>
      </ion-card-header>

      <ion-card-content>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Corporis
        nihil, suscipit facere quae doloremque asperiores deleniti pariatur
        beatae quaerat dolore incidunt ipsa architecto officia, sequi est?
        Minima tempore fugit sint?
      </ion-card-content>
    </ion-card>
  </ion-content>
</template>

<script lang="ts">
import {
  IonHeader,
  IonMenu,
  IonRouterOutlet,
  IonSplitPane,
  IonTitle,
  IonToolbar,
  IonContent,
  IonCard,
  IonCardContent,
  IonCardSubtitle,
  IonCardTitle,
} from "@ionic/vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "Proveedores",
  components: {
    IonHeader,
    IonMenu,
    IonRouterOutlet,
    IonSplitPane,
    IonTitle,
    IonToolbar,
    IonContent,
    IonCard,
    IonCardContent,
    IonCardSubtitle,
    IonCardTitle,
  },
});
</script>