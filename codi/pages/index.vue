<template>
  <v-container fluid>
      <v-row>
          <v-col cols="6">
              PREU
              <v-text-field
              color="white"
              type="number"
              style="max-width:400px" outlined rounded
              v-model="horesMensuals"
              ></v-text-field>
          </v-col>
          <v-col>
              <p style="max-width:600px">
                Si factures {{horesMensuals}} hores al mes, a {{ preuHora }} euros la hora, tens uns ingressos de {{ ingressos }} euros mensuals. 
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
              v-model="preuHora"
              ></v-text-field>
          </v-col>
          <v-col>
            <p style="max-width:600px">
              D'aquests ingressos has de pagar {{iva}} euros a l'estat (21% d'IVA) i aproximadament {{ irpf }} euros a la seguretat social.
            </p>
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
      horesMensuals:0,
      preuHora:0,
      autonoms:300,
      despeses:0,
      souNetDesitjat:0

    }
  },
  computed:{
    /* horesMensualsValidat(){
      return parseInt(this.horesMensuals)
    }, */
    ingressos(){
      return parseInt(this.horesMensuals)*parseInt(this.preuHora)
    },
    iva(){
      return this.ingressos*0.21
    },
    irpf(){
      return this.ingressos*0.15
    },
    eurosNets(){
      return this.ingressos-this.iva-this.irpf-parseInt(this.despeses)-this.autonoms
    },
    
    
    }
  }

</script>