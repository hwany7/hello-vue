<template>

  <div class="menu">
    <a v-for="(m, i) in menu" :key="i">{{ m }}</a>
  </div>

  <img alt="Vue logo" src="./assets/logo.png">

  <div v-for="(p, i) in products" :key="i">
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
          ['역삼동원룸', '60'], 
          ['천호동원룸', '70'], 
          ['마포구원품', '80']
      ],
      menu: ['Home', 'Shop', 'About'],
      num : [0, 0, 0],
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
</style>
