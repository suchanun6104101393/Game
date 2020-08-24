<template>
  <div>
    <button @click="randomStart()" class="btn btn-danger btn-lg ">START!!!{{Label}}</button>
    <button @click="randomDamage()" class="btn btn-dark btn-lg ">ATTACK{{Label}}</button>
    <button @click="randomSpDamage()" class="btn btn-warning btn-lg ">SPECIAL ATTACK{{Label}}</button>
    <div class="row">
      <div class="col-12">
        <div>
          <i1 class="wel">Welcome To Games.</i1>
        </div>
      </div>
    </div>
    <p v-if="hp1 <= -1 ">
      <img
        src="https://wp-media.camdenmarket.com/wp-content/uploads/2019/07/02190505/win-a-vip-experience-at-lockside-camden.gif"
        height="600"
        width="900"
      />
    </p>
    <p v-else-if="hp2 <= -1 ">
      <img
        src="https://media3.giphy.com/media/eJ4j2VnYOZU8qJU3Py/giphy.gif"
        height="600"
        width="900"
      />
    </p>
    <div class="row">
      <div class="col-6">
        <button class="btn btn-dark btn-lg">{{randomPlayer}}</button>
        <p>HP : {{hp1}} %</p>
        <p>{{randomAttack}}</p>
        <img :src="image1" />
      </div>
      <div class="col-6">
        <button class="btn btn-dark btn-lg">{{randomMonster}}</button>
        <p>HP : {{hp2}} %</p>
        <img :src="image2" />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      randomAttack: "",
      randomSpAttack: "",
      image1: "",
      image2: "",
      hp1: "",
      hp2: "",
      player: [
        { name: "BUTTERFREE", hp: 150, image: "./images/Butterfree.png" },
        { name: "CATERPIE", hp: 140, image: "./images/caterpie.png" },
        { name: "FUSHIGISOU", hp: 120, image: "./images/fushigisou.png" },
        { name: "HITOKAGE", hp: 130, image: "./images/hitokage.png" },
        { name: "KAMEIL", hp: 110, image: "./images/kameil.png" },
      ],
      randomPlayer: "",
      //ค่าพลังของ ตัวละคร เข้าถึงโดย player[1].hp -= 20
      monster: [
        { name: "KAMEX", hp: 150, image: "./images/kamex.png" },
        { name: "LIZARDON", hp: 120, image: "./images/lizardon.png" },
        { name: "PIKACHU", hp: 110, image: "./images/pikachu.png" },
        { name: "VAPOREON", hp: 130, image: "./images/vaporeon.png" },
        { name: "ZANIGAME", hp: 140, image: "./images/zanigame.png" },
      ],
      randomMonster: "",
    };
  },
  props: {
    Label: String,
  },
  methods: {
    randomStart: function () {
      var chosenNumber1 = Math.floor(Math.random() * this.player.length);
      this.randomPlayer = this.player[chosenNumber1].name;
      this.hp1 = this.player[chosenNumber1].hp;
      this.image1 = this.player[chosenNumber1].image;
      var chosenNumber2 = Math.floor(Math.random() * this.monster.length);
      this.randomMonster = this.monster[chosenNumber2].name;
      this.hp2 = this.monster[chosenNumber2].hp;
      this.image2 = this.monster[chosenNumber2].image;
    },
    randomDamage: function () {
      this.randomPlayerAttack = Math.max(Math.floor(Math.random() * 10) + 1, 4);
      this.hp2 -= this.randomPlayerAttack;
      this.randomMonsterAttack = Math.max(
        Math.floor(Math.random() * 15) + 1,
        6
      );
      this.hp1 -= this.randomMonsterAttack;
    },
    randomSpDamage: function () {
      this.randomPlayerAttack = Math.max(
        Math.floor(Math.random() * 20) + 1,
        12
      );
      this.hp2 -= this.randomPlayerAttack;
      this.randomMonsterAttack = Math.max(
        Math.floor(Math.random() * 15) + 1,
        5
      );
      this.hp1 -= this.randomMonsterAttack;
    },
  },
};
</script>
<style>
</style>
