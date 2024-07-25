<template>
  <div id="app">
    <h1>Señor del 3</h1>
    <div class="controls">
      <label for="diceCount">Número de Dados: </label>
      <input type="number" id="diceCount" v-model.number="diceCount" min="1" max="10">
    </div>
    <v-btn @click="rollDice" :disabled="rolling">Lanzar Dados</v-btn>
    <div v-if="results.length > 0" class="results">
      <h2>Resultados:</h2>
      <div class="dice-container">
        <img v-for="(result, index) in results" :key="index" :src="require(`./assets/dice/dice${result}.png`)" class="dice" :class="{ rolling: rolling }" />
      </div>
    </div>
    <!--ocho-->
    <v-dialog
      v-model="dialogocho"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         OCHO
        </v-card-title>
        <v-card-text>
POR EL CULO TE LA EMBROCHO        </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogocho = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
<!--kinito-->
    <v-dialog
      v-model="dialogkinito"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         KINITO
        </v-card-title>
        <v-card-text>
MANDATOO        </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogkinito = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  <!--beber y pasar-->
  <v-dialog
      v-model="dialogbeber"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         BEBER Y PASAR
        </v-card-title>
        <v-card-text>
BEBE PUTA        </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogbeber = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
     <!--once-->
  <v-dialog
      v-model="dialogonce"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         ONCE
        </v-card-title>
        <v-card-text>
ONCE       </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogonce = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
      <!--SIETE-->
  <v-dialog
      v-model="dialogsiete"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         SIETE
        </v-card-title>
        <v-card-text>
BEBE IZQUIERDA       </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogsiete = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
     <!--NUEVE-->
  <v-dialog
      v-model="dialognueve"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         NUEVE
        </v-card-title>
        <v-card-text>
BEBE DERECHA       </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialognueve = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <!--tres y uno-->
  <v-dialog
      v-model="dialogtresuno"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         tres y uno
        </v-card-title>
        <v-card-text>
mandas uno      </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogtresuno = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <!--unos-->
  <v-dialog
      v-model="dialogparesuno"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         unos
        </v-card-title>
        <v-card-text>
mandas uno      </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogparesuno = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
     <!--tres y dos-->
  <v-dialog
      v-model="dialogtresdos"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         tres y dos
        </v-card-title>
        <v-card-text>
mandas dos      </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogtresdos = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
     <!--dos-->
  <v-dialog
      v-model="dialogparesdos"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         dos
        </v-card-title>
        <v-card-text>
mandas dos      </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogparesdos = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
     <!--tres-->
  <v-dialog
      v-model="dialogparestres"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         tres
        </v-card-title>
        <v-card-text>
mandas tres      </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogparestres = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <!--cuatro-->
  <v-dialog
      v-model="dialogparescuatro"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         cuatros
        </v-card-title>
        <v-card-text>
OCHO y mandas cuatro      </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogparescuatro = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <!--cinco-->
  <v-dialog
      v-model="dialogparescinco"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         cincos
        </v-card-title>
        <v-card-text>
mandas cinco      </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogparescinco = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <!--seis-->
  <v-dialog
      v-model="dialogparesseis"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         seises
        </v-card-title>
        <v-card-text>
mandas seis      </v-card-text>
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogparesseis = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
     <!--abelardocinco-->
  <v-dialog
      v-model="dialogabelardocinco"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         abelardo al cuatro
        </v-card-title>
        <v-btn @click="rollDiceabelardo" >Lanzar Dado</v-btn>
    
      <h2>Resultados:</h2>
      <div class="dice-container" v-if="resultado>0">
        <img  :src="require(`./assets/dice/dice${resultado}.png`)" class="dice" :class="{ rolling: rolling }" />
      </div>
   
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogabelardocinco = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
     <!--abelardoseis-->
     <v-dialog
      v-model="dialogabelardoseis"
      width="auto"
    >
      <v-card
        max-width="400"
      >
        <v-card-title>
         abelardo al cinco
        </v-card-title>
        <v-btn @click="rollDiceabelardo" >Lanzar Dado</v-btn>
    
      <h2>Resultados:</h2>
      <div class="dice-container" v-if="resultado>0">
        <img  :src="require(`./assets/dice/dice${resultado}.png`)" class="dice" :class="{ rolling: rolling }" />
      </div>
   
        <v-card-actions>
          <v-btn
            class="ms-auto"
            text="Ok"
            @click="dialogabelardoseis = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dialogabelardocinco:false,
      dialogabelardoseis:true,
      dialogtresdos:false,
      dialogparesuno:false,
      dialogparesdos:false,
      dialogparestres:false,
      dialogparescuatro:false,
      dialogparescinco:false,
      dialogparesseis:false,
      dialogtresuno:false,
      dialognueve:false,
      dialogsiete:false,
      dialogonce:false,
      dialogocho: false,
      dialogkinito:false,
      dialogbeber:false,
      diceCount: 2,
      results: [],
      diceabelardo:1,
      resultado:0,
      rolling: false,
      suma: 0,
    };
  },
  methods: {
    rollDiceabelardo(){
      
        this.resultado = Math.floor(Math.random() * 6) + 1;
        
      setTimeout(() => {
        this.rolling = false;
      }, 1000);
    },
    rollDice() {
      this.rolling = true;
      this.results = [];
      this.suma = 0;
     
      for (let i = 0; i < this.diceCount; i++) {
        let num = Math.floor(Math.random() * 6) + 1;
        this.suma = this.suma + num;
        this.results.push(num);
      }
      console.log(this.results);
      if(this.suma==8){
        if(this.results[0]==4 && this.results[1]==4){
          this.dialogparescuatro=true;
        }else{
          this.dialogocho = true;
        }
       
      }else if(this.suma==3){
        this.dialogkinito=true;
      }else if(this.results[0]==6 && this.results[1]==4){
        this.dialogbeber=true;
      }else if(this.results[0]==4 && this.results[1]==6){
        this.dialogbeber=true;
      }else if(this.results[0]==4 && this.results[1]==2){
        this.dialogbeber=true;
      }else if(this.results[0]==2 && this.results[1]==4){
        this.dialogbeber=true;
      }else if(this.suma==11){
        this.dialogonce=true;
      }
      else if(this.suma==7){
        this.dialogsiete=true;
      }else if(this.suma==9){
        this.dialognueve=true;
      }else if(this.results[0]==3 && this.results[1]==1){
        this.dialogtresuno=true;
      }else if(this.results[0]==1 && this.results[1]==3){
        this.dialogtresuno=true;
      }
      else if(this.results[0]==1 && this.results[1]==1){
        this.dialogparesuno=true;
      }else if(this.results[0]==3 && this.results[1]==2){
        this.dialogtresdos=true;
      }else if(this.results[0]==2 && this.results[1]==3){
        this.dialogtresdos=true;
      }else if(this.results[0]==2 && this.results[1]==2){
        this.dialogparesdos=true;
      }else if(this.results[0]==3 && this.results[1]==3){
        this.dialogparestres=true;
      }else if(this.results[0]==5 && this.results[1]==5){
        this.dialogparescinco=true;
      }else if(this.results[0]==6 && this.results[1]==6){
        this.dialogparesseis=true;
      }else if(this.results[0]==5 && this.results[1]==1){
        this.dialogabelardoseis=true;
      }else if(this.results[0]==1 && this.results[1]==5){
        this.dialogabelardoseis=true;
      }else if(this.results[0]==4 && this.results[1]==1){
        this.dialogabelardocinco=true;
      }else if(this.results[0]==1 && this.results[1]==4){
        this.dialogabelardocinco=true;
      }

      setTimeout(() => {
        this.rolling = false;
      }, 1000);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 60px;
}

.controls {
  margin-bottom: 20px;
}

button {
  margin-top: 20px;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}

input[type="number"] {
  width: 50px;
  margin-left: 10px;
}

.results {
  margin-top: 20px;
}

.dice-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.dice {
  width: 100px;
  height: 100px;
  margin: 10px;
  transition: transform 1s;
}

.dice.rolling {
  transform: rotate(360deg);
}
</style>
