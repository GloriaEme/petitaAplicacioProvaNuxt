
<template>
  <v-container fluid>
      <v-row>
          
        
        <v-col class="col">
          Precio TOTAL
          <v-text-field  v-model="precioProducto"  color="black" style="max-width: 400px; " outlined rounded></v-text-field>
        </v-col>
        <v-col class="col"> El cliente paga <strong>{{ precioProducto }} euros</strong> por un producto.</v-col>
      </v-row>
      <v-row>
        <v-col class="col">
          Cost
          <v-text-field  v-model="cost"  color="black" style="max-width: 400px; " outlined rounded></v-text-field>
        </v-col>
        <v-col class="col"> El estado se queda impuestos por el valor de <strong>{{ iva }} euros</strong> (21% de IVA) <br> <br>
           Por tanto el beneficio que te queda a ti como vendedor es de <strong>{{ Ganancia }} euros.</strong> </v-col>
        
      </v-row>
  </v-container>
  </template>
  
  <script>
  export default {
      data(){
          return{
              precioProducto:"",
              cost:"",
              
          }
      },
      computed:{
          iva(){
              return this.precioProducto * 0.21
          },
          Ganancia(){
              return this.precioProducto - this.iva - this.cost
          }
      }
  }
  </script>
  <style>
  body{
    background-color: rgb(166, 236, 233);
    color: rgb(236, 17, 189);
  }
  .col{
  /* min-height: 70vh;
  padding-top: 20vh;
  padding-bottom: 20vh; */
  font-size: 40px;
  }
  
  </style>