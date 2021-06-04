<template>
  <div class="app">
    <h1>カラオケの点数を自慢しよう！</h1>
    <h4>曲名と点数を書いてみて下さい！（記入例)家族になろうよ/ ８５点</h4>
    <input type="text" v-model="score" />
    <button v-on:click="AfterButton">送信</button>
    <img
    src=https://big-echo.jp/wordpress/wp-content/uploads/2013/11/brand_logo_bigecho1_1.gif
    />
  </div>
</template>
<script>
import firebase from "firebase"
export default {
  data() {
    return {
      karaoke: [],
      score: "",
    }
  },
  methods: {
    AfterButton() {
      firebase.firestore().collection("karaoke").add({
        text: this.score,
      })
    },
  },
  created() {
    firebase
      .firestore()
      .collection("karaoke")
      .get()
      .then((snapshot) => {
        snapshot.docs.forEach((doc) => {
          this.karaoke.push({
            id: doc.id,
            ...doc.data(),
          })
        })
      })
  },
}
</script>

<style>
body {
  background-image: url(https://animeanime.jp/imgs/p/jtKDOVlKAvjRrNw8SXAVejagI61Nrq_oqaqr/166385.png);
  background-size: cover;
}
.app {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
}
.app h1 {
  font-size: 60px;
  color: cornflowerblue;
}
</style>
