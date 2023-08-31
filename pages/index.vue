<template>
  <IonPage>
    <ion-header>
      <ion-toolbar>
        <ion-title>Header Toolbar</ion-title>
      </ion-toolbar>
    </ion-header>
    <IonContent class="ion-padding">
      <IonButton> button</IonButton>
      <IonButton router-link="about"> About</IonButton>
      <button class="ml-2 rounded bg-cyan-700 hover:bg-cyan-500 text-white px-4 py-4  w-ful font-bold" @click="$event => router.push('/tailwindcss')">Tailwind CSS Page</button>
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

<script setup lang="ts">
const router = useRouter()
</script>
<style scoped></style>
