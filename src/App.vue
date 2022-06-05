<template>
  <img alt="Logo" src="./assets/images/logo.png" width="150">
  <GetTrivia :categories="categories"  @getData="getData($event)" />
  <AnswerDiv :question=question :answer=answer />
</template>

<script>
import GetTrivia from './components/GetTrivia.vue'
import AnswerDiv from './components/AnswerDiv.vue';


export default {
  name: 'App',
  components: {
    GetTrivia,
    AnswerDiv
},
data(){
    return{
      categories: [],
      question: "",
      answer: "",
  }
  },
  methods: {
    getData(e){
      this.question = e[0].question;
      this.answer = e[0].answer;
    },
  },
  created() {
    this.categories=[
      {
        artliterature:"Art and Literature",
        language:"Language",
        sciencenature:"Science and nature",
        general:"General",
        fooddrink:"Food and drink",
        peopleplaces:"People and places",
        geography:"Geography",
        historyholidays:"History and holidays",
        entertainment:"Entertainment",
        toysgames:"Toys and games",
        music:"Music",
        mathematics:"Mathematics",
        religionmythology:"Religion and mythology",
        sportsleisure:"Sports and leisure"
      }
    ]
    }
  
}

</script>

<style>
body{
  width: 100vw;
  height: 95vh;
  background: rgb(120,159,176);
  background: linear-gradient(0deg, rgba(120,159,176,1) 0%, rgb(59, 90, 103) 100%);
  background-size: cover;
  background-repeat: no-repeat;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
