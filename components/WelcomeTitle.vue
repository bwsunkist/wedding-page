
<template>
  <div class="title">
    <div class="blocks">
      <div class="logo">
        <span>W</span>
        <span class="brink1">el</span>
        <span>co</span>
        <span class="brink2">m</span>
        <span>e</span>
        <br />
        <span>↓↓</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
@import url(//fonts.googleapis.com/css?family=Vibur);

.title {
  width: 100%;
  height: 30%;
}
.blocks {
  width: 100%;
  height: 100%;
  background: #112 url(~/assets/blocks.jpg) center no-repeat;
  background-size: cover;
  margin: 0;
}

.logo {
  position: relative;
  text-align: center;
  color: #fee;
  text-shadow: 0 -40px 100px, 0 0 2px, 0 0 1em #ff4444, 0 0 0.5em #ff4444, 0 0 0.1em #ff4444, 0 10px 3px #000;
  top: 25%;
}

.logo span {
  font: 10vh "Vibur";
}
.brink1 {
  animation: blink linear infinite 2s;
}
.brink2 {
  animation: blink linear infinite 3s;
}

@keyframes blink {
  78% {
    color: inherit;
    text-shadow: inherit;
  }
  79%{
    color: #333;
  }
  80% {
    
    text-shadow: none;
  }
  81% {
    color: inherit;
    text-shadow: inherit;
  }
  82% {
    color: #333;
    text-shadow: none;
  }
  83% {
    color: inherit;
    text-shadow: inherit;
  }
  92% {
    color: #333;
    text-shadow: none;
  }
  92.5% {
    color: inherit;
    text-shadow: inherit;
  }
}
</style>