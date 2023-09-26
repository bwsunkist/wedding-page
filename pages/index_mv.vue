<script setup lang="ts">
</script>

<style>
.home_mv {
  width: 100%;
  height: 100%;
  background: url("../assets/sample2.webp") no-repeat bottom center/cover;
}

.home_mv_text {
  width: 100%;
  position: absolute;
  top: 20%;
}
.home_mv_text h1 span {
  translate: none;
  rotate: none;
  scale: none;
  transform: translate(0px, 0rem);
  opacity: 1;
  visibility: inherit;
  color: cadetblue;
  font-size: 4rem;
  margin-left: 10%;
}
</style>

<template>
  <div class="home_mv"></div>
  <div class="home_mv_text">
    <h1>
      <span>
        Welcome
      </span>
    </h1>
  </div>
</template>