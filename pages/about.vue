<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title>About Page</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempore provident asperiores fuga ullam hic voluptas nostrum, iure sequi rem quasi ex quisquam quam facilis impedit, nam porro est corrupti a.
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
definePageMeta({
  middleware: ['auth'],
})
</script>

<style scoped>

</style>