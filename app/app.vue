<script setup>
useHead({
  meta: [{ name: "viewport", content: "width=device-width, initial-scale=1" }],
  link: [{ rel: "icon", href: "/favicon.ico" }],
  htmlAttrs: {
    lang: "en",
  },
});

const title = "Vélix";
const description =
  "A production-ready starter template powered by Nuxt UI. Build beautiful, accessible, and performant applications in minutes, not hours.";

useSeoMeta({
  title,
  description,
  ogTitle: title,
  ogDescription: description,
  ogImage: "https://ui.nuxt.com/assets/templates/nuxt/starter-light.png",
  twitterCard: "summary_large_image",
});

const route = useRoute();

const items = [
  {
    label: "Bikes",
    to: "/bikes",
    active: route.path.startsWith("/bikes"),
  },
  {
    label: "Cart",
    to: "/cart",
    active: route.path.startsWith("/cart"),
  },
  {
    label: "Login",
    to: "/login",
    active: route.path.startsWith("/login"),
  },
  {
    label: "Signup",
    to: "/signup",
    active: route.path.startsWith("/signup"),
  },
];
</script>

<template>
  <UApp>
    <UHeader class="h-25">
      <template #left>
        <NuxtLink to="/" class="flex items-center gap-5">
          <UIcon name="i-lucide-bike" class="size-15" />
          <p class="text-2xl font-bold uppercase">Vélix</p>
        </NuxtLink>
      </template>

      <UNavigationMenu :items="items" />
      <!-- <template>
        <ULink to="/login" active-class="font-bold" inactive-class="text-muted">
          Connexion
        </ULink>
        <ULink
          to="/signup"
          active-class="font-bold"
          inactive-class="text-muted"
        >
          Inscription
        </ULink>
      </template> -->

      <template #right>
        <UColorModeButton />

        <!-- <UButton
          to="https://github.com/nuxt-ui-templates/starter"
          target="_blank"
          icon="i-simple-icons-github"
          aria-label="GitHub"
          color="neutral"
          variant="ghost"
        /> -->
      </template>
      <template #body>
        <UNavigationMenu
          :items="items"
          orientation="vertical"
          class="-mx-2.5"
        />
      </template>
    </UHeader>

    <UMain>
      <NuxtPage />
    </UMain>

    <USeparator v-text="Hey" />
    <!-- icon="i-simple-icons-nuxtdotjs"  -->

    <UFooter>
      <template #left>
        <p class="text-sm">Vélix • © {{ new Date().getFullYear() }}</p>
      </template>

      <template #right>
        <UIcon name="i-lucide-bike" class="size-8" />
        <UIcon name="i-lucide-bike" class="size-8" />
        <UIcon name="i-lucide-bike" class="size-8" />
      </template>
    </UFooter>
  </UApp>
</template>
