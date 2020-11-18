<template>
  <ion-content >
    <ion-grid>
      <h1>Lista de productos</h1>
    </ion-grid>
   
      <ion-grid v-for="item in items" :key="item.src">
        <ion-row >
          <ion-col size="4">
            <ion-card>
              
              <ion-card-header>
                <ion-card-title>{{ item.title }}</ion-card-title>
              </ion-card-header>

              <ion-card-content>
                <ion-item>
                  <ion-img :src="item.src"></ion-img>
                  </ion-item>
                
                 <h2>Precio $ {{ item.precio }}</h2>
                <ion-label>{{ item.text }}</ion-label>
                <h3>Referencia: {{ item.referencia }} </h3>
                
                <ion-button expand="full">COMPRAR</ion-button>
              </ion-card-content>
               
            </ion-card>
          
          </ion-col>
        </ion-row>
      </ion-grid>
 
  </ion-content>
</template>



<script lang="ts">
import { defineComponent } from "vue";
import {
  IonCard,
  IonCardHeader,
  
  IonCardTitle,
  IonCardContent,
  IonButton,
  IonImg,
  IonItem,
  IonLabel,
  IonGrid,
  IonRow,
  IonCol,
  IonContent,
} from "@ionic/vue";

export default defineComponent({
  name: "Producto",
  components: {
    IonCard,
    IonCardHeader,
   
    IonCardTitle,
    IonCardContent,
    IonButton,
    IonImg,
    IonItem,
    IonLabel,

    IonGrid,
    IonRow,
    IonCol,
    IonContent,
  },
  setup() {
    const items = [
      {
        title: "Anillo X",
        text: "Anillo de oro",
        referencia: "ZVB1",
        precio: "3500",
        src: "/Img/anillo.jpg",
      },
      {
        title: "Anillo Y",
        text: "Anillo de plata",
        referencia: "ZV21",
        precio: "3500",
        src: "/Img/anillo2.jpg",
      },
      {
        title: "Anillo Z",
        text: "Collar de plata ",
        referencia: "Z1B1",
        precio: "3500",
        src: "/Img/collar.jpg",
      },
    ];
    return { items };
  },
});
</script>

