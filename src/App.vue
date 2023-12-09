<template>
  <div>
    <label for="p">+</label>
  <input type="radio" name="op" id="p" value="+" v-model="operator" @change="c()">
</div>
  

  
  <div>
    <label for="m">-</label>
  <input type="radio" name="op" id="m" value="-" v-model="operator" @change="c()">
  
 </div>
  
 
 <br>
  
  <input type="text" id="tb1" v-model.number="num1">
  <input type="text" v-model.number="num2">
  <div id="ac">
    <br>
    {{ answer }}
    
    </div>
</template>

<script>
export default {
  name: 'App',
  data() {
      return {
        num1:'',
        num2:'',
        operator:'',
        answer:''
      }
    },
    methods:{
      c(){
        if (this.num1=='' && this.operator=='-') {
          this.answer=''
        }
       else if (this.operator=='+') {
              this.answer=this.num1+this.num2
            } else if (this.operator=='-'){
              this.answer=this.num1-this.num2
            }
            return this.answer
      }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

#m{
  margin-left: .6%;
}

#tb1{
  margin-right: 1%;
}

#ac{
  margin-left: 11%;
}

</style>
