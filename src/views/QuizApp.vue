<template>
  <h1>Vue クイズ</h1>
  <div class="app">
    <h2>Q. {{ title }}、この人は誰でしょうか？</h2>
    <div id="main">
      <img class="quiz-image" v-bind:src="src" />
    </div>
    <div class="container">
      <input type="text" v-model="inputElement" />
      <br />
      <button id="button" v-on:click="submit">送信！</button>
    </div>
    <div>{{ answer }}</div>
    <button id="button" v-if="seen" v-on:click="next">次の問題へ</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "第1問",
      answer: "正解は、、、",
      inputElement: "",
      Images: [
        { path: require("../assets/k1.webp"), name: "小峠" },
        { path: require("../assets/k2.jpg"), name: "小峠" },
        { path: require("../assets/k3.jpg"), name: "小峠" },
        { path: require("../assets/k5.jpg"), name: "小峠" },
        { path: require("../assets/k6.jpg"), name: "小峠" },
        { path: require("../assets/k7.jpg"), name: "小峠" },
        { path: require("../assets/k8.jpg"), name: "鴨頭" },
        { path: require("../assets/k9.jpg"), name: "正岡子規" },
        { path: require("../assets/k10.jpg"), name: "佐藤" },
      ],
      src: require("../assets/k1.webp"),
      n: 1,
      number: 0,
      now: 0,
      seen: false,
    }
  },
  methods: {
    submit: function () {
      if (this.inputElement == this.Images[this.now].name) {
        this.answer = `正解！${this.Images[this.now].name}です。`
        this.seen = true
      } else if (this.inputElement == "") {
        this.answer = "正解は、、、"
        this.seen = true
      } else {
        this.answer = `残念、${this.Images[this.now].name}でした。`
        this.seen = true
      }
    },
    next: function () {
      this.n++
      this.title = `第${this.n}問`
      this.now = Math.floor(Math.random() * 9)
      this.src = this.Images[this.now].path
      this.answer = "正解は、、、"
      this.inputElement = ""
      this.seen = false
      this.timer = true
    },
  },
}
</script>

<style>
.app {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: center;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  position: relative;
}

.quiz-image {
  height: 300px;
  width: 300px;
  object-fit: contain;
}

#main {
  display: flex;
}
.container {
  height: 5em;
  width: 300px;
  padding: 1em;
  justify-content: center;
  text-align: center;
}

.container input {
  height: 25px;
  width: 150px;
  margin-bottom: 5px;
}

#button {
  margin: 3px;
  color: white;
  background-color: blue;
  appearance: none;
  border: 0px;
  border-radius: 3px;
  height: 40px;
  width: 90px;
}

#timer {
  position: absolute;
  top: 80px;
  left: 60px;
  height: 40px;
  width: 200px;
  font-size: xx-large;
}
</style>
