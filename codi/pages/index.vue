<template>
  <v-container fluid>
      <v-row>
          <v-col cols="6">
              PREU
              <v-text-field
              color="white"
              type="number"
              style="max-width:400px" outlined rounded
              v-model="preuProducte"
              ></v-text-field>
          </v-col>
          <v-col>
            <br>
              <p style="max-width:600px">
                El client paga {{preuProducte}} euros per un producte. 
              </p>
          </v-col>
      </v-row>
      <v-row>
          <v-col>
              COST
              <v-text-field
              color="white"
              type="number"
              style="max-width:400px" outlined rounded
              v-model="preuFinal"
              ></v-text-field>
          </v-col>
          <v-col>
            <p style="max-width:600px">
              L'estat es queda impostos per valor de {{iva}} euros (21% d'IVA). 
              
            </p>

            <p> El producte ens ha costat {{ preuFinal }} </p>
            <p> Per tant, el marge que et queda a tu com a venedor és de {{  }}  euros</p>
          </v-col>
      </v-row>
      <v-row>
          
        
         
      </v-row>
      <v-row>
        <v-col>
          <p>
            {{SioNo}}
          </p>
        </v-col>
      </v-row>
  </v-container>
</template>

<!-- al parseInt li tornes un número -->
<script>
export default{
  data(){
    return{
      preuProducte:"",
      preuFinal:"",
      iva:"",
      guany:""
      

    }
  },
  computed:{
    /* horesMensualsValidat(){
      return parseInt(this.horesMensuals)
    }, */
    preuProducte(){
      return parseInt(this.preuProducte)
    },
    iva(){
      return this.preuProducte*0.21 -this.iva
   
      
    },
    preuFinal(){
      return this.preuFinal-this.iva
    },
    guanyVenedor(){
      return 
    }
    
    
    }
  }

</script>