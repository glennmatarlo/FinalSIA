<template>
  <div class="backdrop">
    <div class="modal">
      <h1>{{title}}</h1>
      <h4>{{text}}</h4>
      <div>
        <input type="text" v-model="s" class=form-control style="margin-top: 20px;width: 70%;" placeholder="Heavenly Body"> 
      </div>
      <div>
         <input type="text" v-model="d" class=form-control style="margin-top: 20px;width: 70%;" placeholder="Distance From Earth (Miles)">
      </div>
      <div>
          <button type="button" class="button1" v-on:click="ans()" style="margin-top: 15px;">Count Minutes</button>
          <button type="button" class="button2" @click="clearData()" style="margin-top: 15px;">Clear Data</button>
      </div>
    <div class="prod">
      <p>
      If we see the ({{s}}) today,we are actually seeing the ({{s}}) as it was {{prod}} minute(s) ago. It took {{prod}} second(s) for the {{s}}'s Light to reach us.  
      </p>                          
    </div> 
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data: function() {
    return {
        text: "Ex. Sun, Distance 93000000 miles",
        title: "FIND LIGHTSPEED",
        d: null,
        s:null,
        prod: 0
    }
    },

    methods:{
        ans(){
            var prod = 0
            var d = parseFloat(this.d)
            prod=(d/186000)/60
            
            this.prod = prod;
            },
      
            clearData(){
            this.d = null;
            this.x = null;
            this.s=null;
            this.prod = 0;
            }
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
  margin-top: 60px;
}
.modal{
  width: 400px;
  padding: 20px;
  margin:100px auto;
  background: rgba(247, 212, 179, 0.74);
  border-radius: 15px;
}
.backdrop{
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
h1{
  color: rgba(15, 15, 15, 0.89);
}
.button1 {
  background-color: #004fa8; /* Green */
  border: none;
  border-radius: 5px;
  color: white;
  margin: 10px;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}
.button2 {
  background-color: #bb020b; /* Green */
  border: none;
  border-radius: 5px;
  margin-left: 10px;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}
input[type=text], select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}
.prod{
  margin-top: 25px;
}
</style>
