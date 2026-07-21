<template>
  <Navbar v-if="!hideLayout" />
  
  <router-view />
  
  <Footer :mode="footerMode" v-if="!hideLayout" />
  
  
</template>

<script setup>
import { computed, onMounted, ref, provide } from "vue"
import { useRoute } from "vue-router"

import Navbar from "./components/layout/Navbar.vue"
import Footer from "./components/layout/Footer.vue"
import { useAuthStore } from "./composables/auth"

const route = useRoute()
const authStore = useAuthStore()

const hideLayout = computed(() =>
  ["giftcards","login","payment", "voucher"].includes(route.name)
)

const footerMode = computed(() =>
  route.name === "home" ? "full" : "simple"
)

const user = ref(JSON.parse(localStorage.getItem("gg-user")) || null)
provide("user", user)

// Restore auth state on every page load / refresh so that
// CheckoutView, AccountView, Navbar, and any other component that
// reads authStore.user gets the correct value without each page
// having to call checkAuth() independently.
onMounted(() => {
  authStore.checkAuth()
})
</script>