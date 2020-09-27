<template>
<div class="vue-3 one-piece">
  <div class="bones">
    <div class="bone"></div>
    <div class="bone"></div>
    <div class="bone"></div>
    <div class="bone"></div>
  </div>
  <div class="head">
    <div class="hat">
      <div class="line-left"></div>
      <div class="line-right"></div>
    </div>
    <div class="eye"></div>
    <div class="eye"></div>
  </div>
  <div class="mouth">
    <div class="teeth"></div>
  </div>
</div>
<h1>{{ msg }}</h1>
<div class="links">
  <a href="https://github.com/vuejs/vue-next/releases/tag/v3.0.0" target="_blank" rel="noreferrer">Release info</a>
  <a href="https://v3.vuejs.org/" target="_blank" rel="noreferrer">Documentation</a>
  <a href="https://v3.vuejs.org/guide/migration/introduction.html" target="_blank" rel="noreferrer">Migration guide</a>
</div>

<div class="author">
  Made with by
  <a href="https://github.com/tanangular/" target="_blank" rel="noreferrer">tanangular</a>
  <p>
    Thank you, Carlos Bonadeo
    <a href="https://codepen.io/cdmoro/pen/XWdyGdb">@CarlosBonadeo</a> for One
    Piece Logo original made
  </p>
</div>
<button @click="count++">count is: {{ count }}</button>
<p>
  Edit <code>components/OnePiece.vue</code> to test hot module replacement.
</p>
</template>

<script>
import {
  ref
} from 'vue'
export default {
  name: 'OnePiece',
  props: {
    msg: String,
  },
  setup() {
    const count = ref(0)

    return {
      count,
    }
  },
}
</script>

<style>
:root {
  --black: #010202;
  --blue: #20526f;
  --green: #00cf74;
  --border-width: 3px;
  --border: var(--black) solid var(--border-width);
}

#app {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  font-family: 'Roboto', sans-serif;
}
</style>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@500&display=swap');

.one-piece {
  position: relative;
  transition: 0.2s;
}

.one-piece:hover {
  transform: scale(1.25);
}

.one-piece .hat {
  width: 100px;
  height: 100px;
  border: var(--border);
  background: var(--blue);
  border-radius: 50%;
  clip-path: inset(0 0 50% 0);
  position: absolute;
  overflow: hidden;
  top: -3px;
}

.one-piece .hat::after {
  content: '';
  height: 12px;
  width: 110%;
  border: var(--border);
  background: var(--green);
  position: absolute;
  top: 36%;
  transform: translatey(-50%);
  left: -10px;
}

.one-piece .hat .line-left {
  position: absolute;
  border-left: var(--border);
  height: 13px;
  left: 28px;
  top: 13px;
  border-radius: 50%;
  width: 5px;
  transform: rotate(34deg);
}

.one-piece .hat .line-left::before {
  content: '';
  position: absolute;
  border-left: var(--border);
  height: 17px;
  left: -10px;
  top: 1px;
  border-radius: 50%;
  width: 5px;
  transform: rotate(0deg);
}

.one-piece .hat .line-left::after {
  content: '';
  position: absolute;
  border-left: var(--border);
  height: 9px;
  left: 5px;
  top: -3px;
  border-radius: 50%;
  width: 3px;
  transform: rotate(-9deg);
}

.one-piece .hat .line-right {
  position: absolute;
  border-right: var(--border);
  height: 15px;
  right: 22px;
  top: 11px;
  border-radius: 50%;
  width: 5px;
  transform: rotate(-30deg);
}

.one-piece .hat .line-right::before {
  content: '';
  position: absolute;
  border-right: var(--border);
  height: 9px;
  right: 7px;
  top: 0px;
  border-radius: 50%;
  width: 4px;
  transform: rotate(11deg);
}

.one-piece .head::before {
  content: '';
  height: 5px;
  width: 150px;
  border: var(--border);
  background: var(--blue);
  position: absolute;
  top: 50%;
  transform: translatey(-8px);
  border-radius: 5px;
  z-index: 1;
}

.one-piece .head::after {
  content: '';
  width: 11px;
  height: 8px;
  border-radius: 50%;
  background: var(--black);
  position: absolute;
  bottom: 8px;
}

.one-piece .head {
  width: 100px;
  height: calc(100px - 0.9rem);
  border: var(--border);
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: flex-end;
  padding-bottom: 0.9rem;
  position: relative;
  background: #fff;
}

.one-piece .eye {
  width: 28px;
  height: 28px;
  background: var(--black);
  border-radius: 50%;
  margin: 0 0.35rem;
}

.one-piece .bone {
  height: 13px;
  width: 50px;
  border: var(--border);
  border-left: none;
  z-index: -1;
  position: absolute;
}

.one-piece .bone::after {
  content: '';
  height: 15px;
  width: 15px;
  border: var(--border);
  border-radius: 50%;
  left: -1px;
  top: 1px;
  position: absolute;
  background: #fff;
  transform: translatex(-18px) translatey(2px) rotate(-90deg);
  clip-path: polygon(50% 100%, 0 100%, 0 0, 100% 0, 100% 25%, 50% 50%);
}

.one-piece .bone::before {
  content: '';
  height: 15px;
  width: 15px;
  border: var(--border);
  border-radius: 50%;
  left: -1px;
  top: 1px;
  position: absolute;
  background: #fff;
  transform: translatex(-18px) translatey(-13px);
  clip-path: polygon(25% 100%, 0 100%, 0 0, 100% 0, 100% 50%, 50% 50%);
}

.one-piece .bone:nth-child(1) {
  transform: rotate(42deg);
  top: 23px;
  left: -26px;
}

.one-piece .bone:nth-child(2) {
  transform: rotate(137deg);
  top: 23px;
  right: -26px;
}

.one-piece .bone:nth-child(3) {
  transform: rotate(313deg);
  bottom: -13px;
  left: 0px;
}

.one-piece .bone:nth-child(4) {
  transform: rotate(227deg);
  bottom: -13px;
  right: 0px;
}

.one-piece .mouth {
  position: absolute;
  height: 120px;
  width: 55px;
  border: var(--border);
  margin: 0 auto;
  border-radius: 50%;
  transform: rotatex(60deg) translatex(-50%);
  left: 50%;
  top: 55px;
  z-index: -1;
  border-width: 4px;
  overflow: hidden;
  background: #fff;
}

.one-piece .mouth::before,
.one-piece .mouth::after {
  content: '';
  width: 70px;
  height: 100px;
  border: var(--border);
  position: absolute;
  border-radius: 50%;
  transform: rotatex(0deg) translatex(-50%);
  left: 50%;
  border-width: 5px;
}

.one-piece .mouth::before {
  top: -52px;
}

.one-piece .mouth::after {
  top: -30px;
}

.one-piece .mouth .teeth {
  position: absolute;
  left: 50%;
  width: var(--border-width);
  height: 46px;
  background: var(--black);
  top: 30px;
  transform: translatex(-50%);
}

.one-piece .mouth .teeth::after,
.one-piece .mouth .teeth::before {
  background: var(--black);
  position: absolute;
  height: 46px;
  width: var(--border-width);
  content: '';
}

.one-piece .mouth .teeth::after {
  transform: translatex(-14px) rotate(3deg);
}

.one-piece .mouth .teeth::before {
  transform: translatex(14px) rotate(-3deg);
}

h1 {
  margin-top: 4.5rem;
  margin-bottom: 0.5rem;
}

a {
  color: #3eaf7c;
}

.links a+a {
  margin-left: 1rem;
}

.author {
  margin-top: 1rem;
}

.author code {
  color: tomato;
  font-weight: bold;
}
</style>
