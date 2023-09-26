<template>
  <div class="title">
    <div class="blocks">
      <link href='https://fonts.googleapis.com/css?family=Sacramento:400' rel='stylesheet' type='text/css'>
      <NuxtLink to="/groom">
        <h1 class="neonText-g">
          Groom
        </h1>
      </NuxtLink>
      <NuxtLink to="/bride">
        <h1 class="neonText-b">
          Bride
        </h1>
      </NuxtLink>
    </div>
  </div>
</template>

<style scoped>
@import url(//fonts.googleapis.com/css?family=Vibur);

.title {
  width: 100%;
  height: 50%;
}
.blocks {
  width: 100%;
  height: 100%;
  background: #112 url(~/assets/blocks_rev.jpg) center no-repeat;
  background-size: cover;
  margin: 0;
}

h1 {
  text-align: center;
  font-weight: 250;
  margin-right: 10%;
  margin-left: 10%;
  margin-top: 10%;
}

.neonText-g {
  color: #fff;
  text-shadow:
    0 0 7px #fff,
    0 0 10px #fff,
    0 0 21px #fff,
    0 0 42px #08f,
    0 0 82px #08f,
    0 0 92px #08f,
    0 0 102px #08f,
    0 0 151px #08f;
  font-family: "Sacramento", sans-serif;
  font-size: 8vh;
  animation: pulsate-g 1.5s infinite alternate;  
  border: 0.2rem solid #fff;
  border-radius: 2rem;
  padding: 0.2em;
  box-shadow: 0 0 .2rem #fff,
            0 0 .2rem #fff,
            0 0 2rem #08f,
            0 0 0.8rem #08f,
            0 0 2.8rem #08f,
            inset 0 0 1.3rem #08f; 
}

@keyframes pulsate-g {
  100% {
      text-shadow:
      0 0 4px #fff,
      0 0 11px #fff,
      0 0 19px #fff,
      0 0 40px #08f,
      0 0 80px #08f,
      0 0 90px #08f,
      0 0 100px #08f,
      0 0 150px #08f;
  }  
  0% {
    text-shadow:
    0 0 2px #fff,
    0 0 4px #fff,
    0 0 6px #fff,
    0 0 10px #08f,
    0 0 45px #08f,
    0 0 55px #08f,
    0 0 70px #08f,
    0 0 80px #08f;
  }
}

.neonText-b {
  color: #fff;
  text-shadow:
    0 0 7px #fff,
    0 0 10px #fff,
    0 0 21px #fff,
    0 0 42px #f40,
    0 0 82px #f40,
    0 0 92px #f40,
    0 0 102px #f40,
    0 0 151px #f40;
  font-family: "Sacramento", sans-serif;
  font-size: 8vh;
  animation: pulsate-b 1.5s infinite alternate;  
  border: 0.2rem solid #fff;
  border-radius: 2rem;
  padding: 0.2em;
  padding-top: 0.3em;
  padding-bottom: 0.1em;
  box-shadow: 0 0 .2rem #fff,
            0 0 .2rem #fff,
            0 0 2rem #f40,
            0 0 0.8rem #f40,
            0 0 2.8rem #f40,
            inset 0 0 1.3rem #f40; 
}

@keyframes pulsate-b {
  100% {
      text-shadow:
      0 0 4px #fff,
      0 0 11px #fff,
      0 0 19px #fff,
      0 0 40px #f40,
      0 0 80px #f40,
      0 0 90px #f40,
      0 0 100px #f40,
      0 0 150px #f40;
  }  
  0% {
    text-shadow:
    0 0 2px #fff,
    0 0 4px #fff,
    0 0 6px #fff,
    0 0 10px #f40,
    0 0 45px #f40,
    0 0 55px #f40,
    0 0 70px #f40,
    0 0 80px #f40;
  }
}

</style>