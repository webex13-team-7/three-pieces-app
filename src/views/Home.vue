<template>
  <h1>Home</h1>
  <div class="home">
    <router-link to="/memo" class="nav__link">
      <div class="word">メモ</div>
    </router-link>
    <router-link to="/palette" class="nav__link1">
      <div class="word">パレット</div>
    </router-link>
    <router-link to="/quiz" class="nav__link">
      <div class="word">クイズ</div>
    </router-link>
  </div>
</template>

<style scoped>
.home {
  width: 1000px;
  margin: 0 auto;
  display: flex;
  text-align: center;
  font-size: 50px;
}

.nav__link {
  width: 300px;
  height: 200px;
  background-color: #41b883;
  color: #2c3e50;
  text-decoration: none;
  border-radius: 20px;
  box-shadow: 2px 3px 2px 1px #2c3e50;
}

.nav__link:hover {
  width: 290px;
  height: 190px;
  color: red;
}
.nav__link1 {
  width: 300px;
  height: 200px;
  background-color: #42b983;
  color: #2c3e50;
  margin: 0 20px;
  vertical-align: middle;
  text-decoration: none;
  border-radius: 20px;
  box-shadow: 2px 3px 2px 1px #2c3e50;
}

.nav__link1:hover {
  width: 290px;
  height: 190px;
  color: red;
}
.word {
  margin-top: 15%;
}
</style>
