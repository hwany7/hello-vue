<template>

  <div class="black-bg" v-if="open_modal == ture">
    <div class="white-bg">
      <h4>[상세 페이지]</h4>
      <p>상세 내용</p>
      <button @click="open_modal = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(m, i) in menu" :key="i">{{ m }}</a>
  </div>

  <div v-for="(p, i) in products" :key="i">
    <img @click="open_modal = ture" src="./assets/room0.jpg" class="room-img">
    <h4 :style="스타일">{{ p[0] }}</h4>
    <p> {{ p[1] }} 만원 </p> 
    <button @click="plus_num(i)">매물신고</button> <span>신고수: {{ num[i] }}</span>
  </div>

</template>


<script>

export default {
  name: 'App',
  data(){
    return {
      스타일 : 'color : red',
      products : [
          ['역삼동원룸', '60', './assets/room0.jpg'], 
          ['천호동원룸', '70', './assets/room1.jpg'], 
          ['마포구원품', '80', './assets/room2.jpg']
      ],
      menu: ['Home', 'Shop', 'About'],
      num : [0, 0, 0],
      open_modal : false,
    }
  },
  methods : {
    plus_num(i){
      this.num[i]++;
    }
  },
  components: {
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;
}
.room-img{
  width: 100%;
  margin-top: 40px;
}
.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; 
  padding: 20px;
}
.white-bg{
  width: 80%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
