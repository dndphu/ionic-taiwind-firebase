<template>
  <IonPage>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title>Header Toolbar</ion-title>
      </ion-toolbar>
    </ion-header>
    <IonContent class="ion-padding">
      <IonButton> button</IonButton>
      <IonButton router-link="about"> About</IonButton>
      <ion-card>
        <ion-card-header>
          <ion-card-title>Card Title</ion-card-title>
          <ion-card-subtitle>Card Subtitle</ion-card-subtitle>
        </ion-card-header>

        <ion-card-content>
          Here's a small text description for the card content. Nothing more,
          nothing less.
        </ion-card-content>
      </ion-card>
    </IonContent>
  </IonPage>
</template>

<script lang="ts">
// import {
//   IonCard,
//   IonCardContent,
//   IonCardHeader,
//   IonCardSubtitle,
//   IonCardTitle,
// } from "@ionic/vue";
</script>
<style scoped></style>
