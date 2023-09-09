<template>
  <RenderWhen context="main">
    <AsciinemaPlayer :src="src" :playerProps="playerProps" />
  </RenderWhen>
</template>

<script setup>
import AsciinemaPlayer from "./AsciinemaPlayer.vue";
import RenderWhen from "@slidev/client/builtin/RenderWhen.vue";

const props = defineProps(["src", "playerProps"]);
</script>
