<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Header Toolbar</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <ion-button @click="onLogout"> Logout</ion-button>
      <ion-button v-if="!auth" router-link="login"> Login</ion-button>
      <ion-button router-link="about"> About</ion-button>
      <!-- <button
        class="ml-2 rounded bg-cyan-700 hover:bg-cyan-500 text-white px-4 py-4 w-ful font-bold"
        @click="($event) => router.push('/tailwindcss')"
      >
        Tailwind CSS Page
      </button> -->
      <ion-card>
        <ion-card-header>
          <ion-card-title>Card Title</ion-card-title>
          <ion-card-subtitle>Card Subtitle</ion-card-subtitle>
        </ion-card-header>

        <ion-card-content>
          {{ auth }}
        </ion-card-content>
      </ion-card>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
const auth = useFirebaseAuth()?.currentUser;
const router = useRouter();
definePageMeta({
  middleware: ["auth"],
});

const onLogout = async () => {
  await useFirebaseAuth()?.signOut();
  router.replace("/login");
};
</script>
<style scoped></style>
