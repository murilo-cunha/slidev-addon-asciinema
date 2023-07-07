<template>
    <div :id="src" />
</template>

<script>
import * as AsciinemaPlayer from "asciinema-player";

export default {
  props: ["src", "playerProps"],
  mounted() {
    AsciinemaPlayer.create(import.meta.env.BASE_URL + this.src, document.getElementById(this.src), this.playerProps);
  },
};
</script>

<style>
@import "./asciinema-player.css";
</style>
