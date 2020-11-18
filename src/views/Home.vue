<template>
    <ion-page>
        <ion-header :translucent="true">
            <ion-toolbar>
                <ion-title>Blank</ion-title>
            </ion-toolbar>
        </ion-header>
        <ion-content :fullscreen="true">
            <ion-header collapse="condense">
                <ion-toolbar>
                    <ion-title size="large">Blank</ion-title>
                </ion-toolbar>
            </ion-header>
            <ion-card>
                <ion-card-header>
                    <ion-card-subtitle>Control de acceso</ion-card-subtitle>
                    <ion-card-title>Ingresar</ion-card-title>
                </ion-card-header>
                <ion-card-content>
                    <ion-item>
                        <ion-label position="floating">Username</ion-label>
                        <ion-input name="Username" :value="mydata.username" @input="mydata.username = $event.target.value"></ion-input>
                    </ion-item>
                    <ion-item>
                        <ion-label position="floating">Password</ion-label>
                        <ion-input name="Password" type="password" :value="mydata.password" @input="mydata.password = $event.target.value"></ion-input>
                    </ion-item>
                    <IonButton expand="block" color="primary" @click="onIngresarClick()">Ingresar</IonButton>
                    <a href="register">Registrar</a>

                </ion-card-content>
            </ion-card>
        </ion-content>
    </ion-page>
</template>
<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButton, alertController } from '@ionic/vue';
import { defineComponent } from 'vue';
import axios from 'axios';

export default defineComponent({
    name: 'Home',
    data() {
        return {
            mydata : {
                username : "",
                password : "",
            },
        }
    },

    components: {
        IonContent,
        IonHeader,
        IonPage,
        IonTitle,
        IonToolbar,
        IonButton,
    },
    
    methods: {
        async onIngresarClick() {
            try{

         const res = await axios.get('http://localhost:3000/ERROR', {params : this.mydata});

            console.log(res);
            if (res.data.code === 'OK'){
                const alert = await alertController
                .create({
                    header: 'Acceso concedido',
                    message: res.data.message,
                    buttons: ['OK'],
                });
                return alert.present();    
            }else{
                const alert = await alertController
                .create({
                    header: 'ERROR',
                    message: res.data.message,
                    buttons: ['OK'],
                });
            return alert.present();    
            }
            

            }catch(e){
                console.log(e);
            }
              
            
        }
    }, //methods
});
</script>
<style scoped>
#container {
    text-align: center;

    position: absolute;
    left: 0;
    right: 0;
    top: 50%;
    transform: translateY(-50%);
}

#container strong {
    font-size: 20px;
    line-height: 26px;
}

#container p {
    font-size: 16px;
    line-height: 22px;

    color: #8c8c8c;

    margin: 0;
}

#container a {
    text-decoration: none;
}

</style>
