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
                
                 <h2>Precio $: {{ item.precio }}</h2>
                <ion-label>{{ item.text }}</ion-label>
                <h3>Código: {{ item.referencia }} </h3>
                
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
        
        title: "Anillo de compromiso plata",
        text: "22k",
        referencia: "H6N3",
        precio: "25,500",
        src: "/Img/compromiso.jpg",
      },
      {
        title: "Anillo de oro",
        text: "14k",
        referencia: "AD3V1",
        precio: "15,500",
        src: "/Img/anillo.jpg",
      },
      {
        title: "Anillo de oro, diamante esmeralda",
        text: "10k",
        referencia: "ZV21",
        precio: "20,500",
        src: "/Img/anillo2.jpg",
      },
     
       {
        title: "Pulsera oro rigida",
        text: "5k",
        referencia: "K6B0",
        precio: "1,500",
        src: "/Img/pulsera.jpg",
      },
      {
        title: "Brazalete de pulsera de alambre expandible de oro",
        text: "8k",
        referencia: "P925",
        precio: "2,500",
        src: "/Img/brazalete.jpg",
      },
        {
        title: "Brazalete cupido, bronce baño de oro",
        text: "22k",
        referencia: "V9K7",
        precio: "12,500",
        src: "/Img/brazaletecupido.jpg",
      },
      {
        title: "Reloj Michael Kors DAMA",
        text: "28k",
        referencia: "M6K8",
        precio: "20,000",
        src: "/Img/reloj.jpg",
      },
       {
        title: "Reloj para hombres Michael Kors",
        text: "30k",
        referencia: "M8K1",
        precio: "25,000",
        src: "/Img/relojh.jpg",
      },
       {
        title: "Reloj Michael Kors DAMA",
        text: "25k",
        referencia: "M5K1",
        precio: "17,000",
        src: "/Img/relojm.jpg",
      },
       {
        title: "Arracadas de oro amarillo",
        text: "14k",
        referencia: "A5O9",
        precio: "3000",
        src: "/Img/aretes.jpg",
      },
      {
        title: "Aretes de oro, corazon mediano",
        text: "10k",
        referencia: "A5O9",
        precio: "940",
        src: "/Img/aretes1.jpg",
      },
      {
        title: "Aretes de oro, diamante esmeralda",
        text: "14k",
        referencia: "O6N2",
        precio: "11,591",
        src: "/Img/aretes2.jpg",
      },
    ];
    return { items };
  },
});
</script>

