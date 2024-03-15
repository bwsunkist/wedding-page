<template>
  <div class="all">
    <div class="modal-all" v-show="isDisplayModal">
      <div class="modal-window">
        <span class="modal-close" v-on:click="closeModal">&times;</span>
        <br>
        <div class="modal-navi">
          <p>
            <br>
            << 隠し要素 >>
            <br>
            ハイスコアを目指してね！
          </p>
          <button class="modal-button"
              onclick="location.href='https://bwsunkist.github.io/memorial-ar/minigame'">
              ミニゲームを遊ぶ
          </button>
          <br>
          <br>
          <button class="modal-button"
              v-on:click="closeModal">
              今は遊ばない
          </button>
        </div>
      </div>
    </div>
    <div class="cmd" v-show="isDisplayCmd">
      <p>{{ cmdHistoryStr }}</p>
    </div>
    <div class="home_mv" v-touch:longtap="onLongTap">
      <img src="../assets/sample2.webp" class="home_mv_img">
    </div>
    <div class="home_mv_text">
      <h1 v-touch:tap="onTap"
        v-touch:swipe.left="onSwipeLeft"
        v-touch:swipe.right="onSwipeRight"
        v-touch:swipe.top="onSwipeUp"
        v-touch:swipe.bottom="onSwipeDown"
      >
          Welcome
      </h1>
    </div>
    <div class="home_mv_scroll blinking">
      <span>
        SCROLL↓
      </span>
      <span class="arrow arrow--down arrow--white"></span>
    </div>
    <div class="message">
      <h2>
        ご挨拶
      </h2>
      <br>
      <p>
        この度はご多用の中
        <br>
        私たちの結婚式・披露宴に
        <br>
        ご列席くださりありがとうございます
        <br>
        <br>
        当日を迎えるにあたり
        <br>
        私たちのことを
        <br>
        もっと知ってもらえればと思い
        <br>
        自己紹介ページを準備しました
        <br>
        ぜひご覧ください
        <br>
        <br>
        誠博　映里奈
      </p>
    </div>
    <div class="cp_arrows">
      <div class="cp_arrow"></div>
      <div class="cp_arrow"></div>
      <div class="cp_arrow"></div>
    </div>
    <div class="navi">
      <a href="https://akita-pages.notion.site/Bride-Erina-Profile-f10f3907207b4fb8b3da19736bdcf56c?pvs=4" class="btn btn-malformation">> Bride</a>
      <a href="https://akita-pages.notion.site/Groom-Masahiro-Profile-74dd63394ae74169be2da4e374021b54?pvs=4" class="btn btn-malformation2">> Groom</a>
    </div>
  </div>
</template>

<script setup>
  import { ref } from "vue";

  let count = 0;
  const isDisplayModal = ref(false);
  const isDisplayCmd = ref(false);
  const cmdHistory = ref([]);

  const cmdHistoryStr = computed(() => {
    return cmdHistory.value.join();
  })

  const onTap = () => {
    if(cmdHistory.value[cmdHistory.value.length -1] == "tap") {
      count++;
      console.log("before cmd is tap", cmdHistory.value[cmdHistory.value.length -1])
    } else {
      console.log("before cmd is not tap", cmdHistory.value[cmdHistory.value.length -1])
      count = 1;
    }
    cmdHistory.value.push("tap");
    checkTapCount();
    checkHistory();
  };

  const onLongTap = () => {
    isDisplayCmd.value = !isDisplayCmd.value;
    console.log("longTap");
  };

  const onSwipeLeft = () => {
    console.log("swipeLeft");
    cmdHistory.value.push("←");
    checkHistory();
  };
  const onSwipeRight = () => {
    console.log("swipeRight");
    cmdHistory.value.push("→");
    checkHistory();
  };
  const onSwipeUp = () => {
    console.log("swipeUp");
    cmdHistory.value.push("↑");
    checkHistory();
  };
  const onSwipeDown = () => {
    console.log("swipeDown");
    cmdHistory.value.push("↓");
    checkHistory();
  };

  const checkTapCount = () => {
    if(count == 10) {
      isDisplayModal.value = true;
      console.log("debug:trigger tap")
      count = 0;
    }
  }

  const checkHistory = () => {
    if (cmdHistory.value.length == 11 ) {
      cmdHistory.value.shift()
    }
    const konami =  ["↑","↑","↓","↓","←","→","←","→","tap","tap"];
    const konamiStr = konami.join();
    if(cmdHistory.value.join() == konamiStr) {
      console.log("debug:trigger konami")
      cmdHistory.value = [];
    }
  }

  const closeModal = () => {
    console.log("modal close");
    isDisplayModal.value = false;
    cmdHistory.value = [];
  }

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400;700&display=swap');

.all {
  width: 100%;
  height: 100%;  
  max-width: 430px;
  margin: auto;
  font-family: "Noto Sans JP", "Hiragino Kaku Gothic ProN", Meiryo, sans-serif;
}

.cmd {
  position: fixed;
  top:1%
}
.cmd p {
  color:cadetblue;
  font-size: 1.5rem;
}

.home_mv {
  width: 100%;
  height: 100%;
  margin-left: auto;
  margin-right: auto;
}

.home_mv_img {
  width: 100%;
  height: 100%;
}

.home_mv_text {
  width: 20rem;
  top: 7%;
  left: 10%;
  position: absolute;
}
.home_mv_text h1 {
  translate: none;
  rotate: none;
  scale: none;
  transform: translate(0px, 0rem);
  opacity: 1;
  visibility: inherit;
  color:cadetblue;
  font-size: 4rem;
}
.home_mv_text h1:before{
	content: '';
	position: absolute;
	left: 0;
	bottom: 0;
	border-bottom: solid 3px cadetblue;
	animation: border_anim 5s linear forwards;
}
@keyframes border_anim {
	0%{
		width: 0%;
	}
	100%{
		width: 100%;
	}
}
.home_mv_scroll {
  top: 93%;
  left: 10%;
  font-size: 1rem;
  position: absolute;
  color: cadetblue;
  font-weight: 800;
}
.blinking{
	-webkit-animation:blink 1.2s ease-in-out infinite alternate;
    -moz-animation:blink 1.2s ease-in-out infinite alternate;
    animation:blink 1.2s ease-in-out infinite alternate;
}
@-webkit-keyframes blink{
    0% {opacity:0;}
    100% {opacity:1;}
}
@-moz-keyframes blink{
    0% {opacity:0;}
    100% {opacity:1;}
}
@keyframes blink{
    0% {opacity:0;}
    100% {opacity:1;}
}

.message {
  width: 100%;
  background-color:snow;
  padding-bottom: 10%;
}
.message h2 {
  margin: 0;
  padding-top: 20%;
  text-align: center;
  font-size: 1.7rem;
}
.message p {
  margin-top: 0;
  text-align: center;
}

.navi {
  width: 100%;
  background-color: snow;
  text-align: center;
  padding-top: 12%;
  padding-bottom: 20%;
}
.navi h2 {
  margin-bottom: 0;
  text-align: center;
  font-size: 1.7rem;
}

.modal-all {
  position: absolute;
  background-color: darkgrey;
  width: 100%;
  height: 300%;

  z-index: 10;
}

.modal-window {
  position: fixed;
  background-color: white;
  width: 60%;
  height: 50%;
  top: 20%;
  left: 20%;
}

.modal-navi {
  background-color: white;
  text-align: center;
  vertical-align: middle;
}

.modal-close {
    color: #aaaaaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
}

.btn,
a.btn {
  font-size: 1.6rem;
  font-weight: 700;
  line-height: 1.5;
  position: relative;
  display: inline-block;
  padding: 1rem 4rem;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  -webkit-transition: all 0.3s;
  transition: all 0.3s;
  text-align: center;
  vertical-align: middle;
  text-decoration: none;
  letter-spacing: 0.1em;
  color: #212529;
  border-radius: 0.5rem;

  margin-bottom: 6%;
}

a.btn-malformation {
  font-size: 2rem;

  padding: 3rem 4rem;

  color: #fff;
  border-radius: 100% 80px / 80px 100%;
  background-color: #eb6100;
}

a.btn-malformation2 {
  font-size: 2rem;

  padding: 3rem 4rem;

  color: #fff;
  border-radius: 100% 80px / 80px 100%;
  background-color:yellowgreen;
}

.cp_arrows *, .cp_arrows *:before, .cp_arrows *:after {
	-webkit-box-sizing: border-box;
    box-sizing: border-box;
  }
.cp_arrows {
  background-color: snow;
  position: relative;
	display: flex;
	height: 120px;
	margin: auto;
	justify-content: center;
	align-items: center;
  text-align: center;
}
.cp_arrows .cp_arrow {
	position: absolute;
	width: 60px;
	height: 10px;
	-webkit-transform: scale(0.3);
    transform: scale(0.3);
	-webkit-animation: arrow-move07 3s ease-out infinite;
    animation: arrow-move07 3s ease-out infinite;
	opacity: 0;
}
.cp_arrows .cp_arrow:first-child {
	-webkit-animation: arrow-move07 3s ease-out 1s infinite;
    animation: arrow-move07 3s ease-out 1s infinite;
}
.cp_arrows .cp_arrow:nth-child(2) {
	-webkit-animation: arrow-move07 3s ease-out 2s infinite;
    animation: arrow-move07 3s ease-out 2s infinite;
}
.cp_arrows .cp_arrow:before,
.cp_arrows .cp_arrow:after {
	position: absolute;
	top: 0;
	width: 50%;
	height: 100%;
	content: '';
	border-radius: 2px;
	background: cadetblue;
}
.cp_arrows .cp_arrow:before {
	left: 1px;
	-webkit-transform: skewY(30deg);
    transform: skewY(30deg);
}
.cp_arrows .cp_arrow:after {
	right: 1px;
	width: 50%;
	-webkit-transform: skewY(-30deg);
    transform: skewY(-30deg);
}
@-webkit-keyframes arrow-move07 {
	25% {
		opacity: 0.6;
	}
	43.75% {
		-webkit-transform: translateY(1em);
      transform: translateY(1em);
		opacity: 0.8;
	}
	62.5% {
		-webkit-transform: translateY(2em);
      transform: translateY(2em);
		opacity: 1;
	}
	100% {
    -webkit-transform: translateY(3em) scale(0.5);
      transform: translateY(3em) scale(0.5);
		opacity: 0;
	}
}
@keyframes arrow-move07 {
	25% {
		opacity: 0.6;
	}
	43.75% {
		-webkit-transform: translateY(1em);
      transform: translateY(1em);
		opacity: 0.8;
	}
	62.5% {
		-webkit-transform: translateY(2em);
      transform: translateY(2em);
		opacity: 1;
	}
	100% {
		-webkit-transform: translateY(3em) scale(0.5);
      transform: translateY(3em) scale(0.5);
		opacity: 0;
	}
}
</style>
