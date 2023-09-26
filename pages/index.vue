<script setup lang="ts">
import WelcomeTitle from '~/components/WelcomeTitle.vue'
import WelcomeMessage from '~/components/WelcomeMessage.vue'
import WelcomeNavigation from '~/components/WelcomeNavigation.vue'
</script>

<style>
.messages {
  width: 100%;
  height: 50%;
  color: #fee;
  font: 3vh "Vibur";
}
</style>

<template>
  <WelcomeTitle></WelcomeTitle>
  <WelcomeMessage></WelcomeMessage>
  <WelcomeNavigation></WelcomeNavigation>
</template>