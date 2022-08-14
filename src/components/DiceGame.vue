<template>
  <div class="gameArea">
       
        <div id="player1">{{player1}}</div>
        <div id="player2">{{player2}}</div>
        <div id="output" v-if="player1>player2">{{output2}}</div>
        <div id="output" v-if="player1<player2">{{output3}}</div>
        <div id="output" v-if="player1==player2">{{output1}}</div>


        
        
    </div>
    <button type="button" @click="random(6)">Roll</button>
</template>

<script>
export default {
  name: 'DiceGame',
  
  
  data(){
    return {
      player1: 0,
      player2: 1,
      output1: "It was a draw",
      output2: "Player 1 wins",
      output3: "Player 2 wins",
      num: 6,
    
      }
  },


   methods: {
      random(){
            this.player1 = Math.floor(Math.random()*this.num)+1;
            this.player2 = Math.floor(Math.random()*this.num)+1;
                  
      },


   }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 #player1, #player2{
            display: inline-block;
            width: 200px;
            height: 140px;
            border: 1px solid black;
            padding: 5px;
            margin: 25px;
            text-align: center;
            font-size: 7em;

        }

        #output{
              text-align: center;
            font-size: 2em;
        }

        button{
            padding: 10px;
            text-align: center;
            width: 550px;
        }
</style>
