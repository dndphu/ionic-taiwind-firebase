<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title>Login page</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding">
      <div class="bg-white shadow-xl p-10 flex flex-col gap-4 text-sm">
        <div>
          <label class="text-gray-600 font-bold inline-block pb-2" for="email"
            >Email</label
          >
          <input
            v-model="credentials.email"
            class="border border-gray-400 focus:outline-slate-400 rounded-md w-full shadow-sm px-5 py-2"
            type="email"
            name="email"
            placeholder="xxx@gmail.com"
            autocapitalize="none"
            autocomplete="none"
          />
        </div>
        <div>
          <label
            class="text-gray-600 font-bold inline-block pb-2"
            for="password"
            >Password</label
          >
          <input
            v-model="credentials.password"
            class="border border-gray-400 focus:outline-slate-400 rounded-md w-full shadow-sm px-5 py-2"
            type="password"
            name="password"
            placeholder="******"
            autocapitalize="none"
            autocomplete="none"
          />
        </div>
        <div class="flex">
          <div class="w-1/2">
            <input type="checkbox" name="remeberMe" />
            <label for="remeberMe">Remeber me</label>
          </div>
          <div class="w-1/2">
            <a class="font-bold text-blue-600" href="">Forgot password ?</a>
          </div>
        </div>
        <button
          @click="onSignIn"
          class="bg-[#4F46E5] w-full py-2 rounded-md text-white font-bold cursor-pointer hover:bg-[#181196]"
        >
          Login
        </button>
        <!-- <div>
          <p class="text-center">Or continue with</p>
        </div> -->
        <!-- <div>
          <button class="bg-cyan-400	py-4 px-4 rounded font-bold">
            Sign In
          </button>
        </div> -->
        <!-- <div class="flex gap-4">
          <button
            class="bg-[#1D9BF0] w-1/2 py-1 rounded-md text-white font-bold cursor-pointer hover:bg-[#181196]"
          >
            Google
          </button>
          <button
            class="bg-[#24292F] w-1/2 py-1 rounded-md text-white font-bold cursor-pointer hover:bg-[#181196]"
          >
            Github
          </button>
        </div> -->
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { Auth, signInWithEmailAndPassword } from "firebase/auth";
const router = useRouter();
const route = useRoute();

const auth = useFirebaseAuth();
const credentials = reactive({
  email: "",
  password: "",
});

const onSignIn = async () => {
  console.log("credentials :>> ", credentials);
  try {
    const { email, password } = credentials;
    const authRes = await signInWithEmailAndPassword(
      auth as Auth,
      email,
      password
    );
    if (!authRes?.user) throw Error("No User");
    console.log("authRes :>> ", authRes);
    const { query, params } = route;
    router.replace((query as any)?.redirect ?? "/");
  } catch (error) {
    alert((error as Error)?.message);
  }
};
</script>

<style scoped></style>
