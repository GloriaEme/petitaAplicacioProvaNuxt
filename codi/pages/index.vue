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
      preuProducte:0,
      despeses:0,
      souNetDesitjat:0

    }
  },
  computed:{
    /* horesMensualsValidat(){
      return parseInt(this.horesMensuals)
    }, */
    ingressos(){
      return parseInt(this.preuProducte)
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