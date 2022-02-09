<template>
  <q-page
    class="bg-light-green window-height window-width row justify-center items-center"
  >
    <div class="column">
      <div class="row">
        <h5 class="text-h5 text-white q-my-md">Company & Co</h5>
      </div>
      <div class="row">
        <q-card square bordered class="q-pa-lg shadow-1">
          <q-card-section>
            <q-form class="q-gutter-md">
              <q-input
                square
                filled
                clearable
                v-model="email"
                type="email"
                label="email"
              />
              <q-input
                square
                filled
                clearable
                v-model="password"
                type="password"
                label="password"
              />
            </q-form>
          </q-card-section>
          <q-card-actions class="q-px-md">
            <q-btn
              unelevated
              color="light-green-7"
              size="lg"
              class="full-width"
              label="Login"
              @click="isValidLogin()"
            />
          </q-card-actions>
          <q-card-section class="text-center q-pa-none">
            <p class="text-grey-6">Not reigistered? Created an Account</p>
          </q-card-section>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script>
import { ref } from "@vue/reactivity";
import { useRouter } from "vue-router";
export default {
  name: "PageIndex",
  setup() {
    const router = useRouter();
    const email = ref("");
    const password = ref("");

    const isValidLogin = () => {
      if (email.value === "demo@demo.com" && password.value === "demo") {
        console.log("Login successful");
        router.push("/register");
      }
    };
    return {
      email,
      password,
      isValidLogin,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
  // data() {
  //   return {
  //     email: "",
  //     password: "",
  //   };
  // },
  // methods: {
  //   isValidLogin() {
  //     if (this.email === "demo@demo.com" && this.password === "demo") {
  //       console.log("Login successful");
  //       $router.push("/register");
  //     }
  //   },
  // },
};
</script>

<style>
.q-card {
  width: 360px;
}
</style>
