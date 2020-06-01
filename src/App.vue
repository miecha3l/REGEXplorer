<template>
  <div id="app">
    <h1>REGEXplorer</h1>
    <RegexInput v-bind:update="updateResult" v-bind:eval="evaluateExpression"/>
    <Output v-bind:data="result"/>
    <Console v-bind:errMsg="error"/>
  </div>
</template>

<script>
import RegexInput from './components/RegexInput'
import Output from './components/Output'
import Console from './components/Console'

export default {
  name: 'App',
  components: {
    RegexInput,
    Output,
    Console
  },
  data() {
    return {
      result: "",
      regex: "",
      error: "",
    }
  },
  methods: {
    'updateResult': function(input, regex) {
      this.result = input;
      this.regex = regex;
    },

    'evaluateExpression': function() {
      if(this.regex.length > 0){
        try{
          this.result = this.result.replace(new RegExp(this.regex, 'gi'), str => `<span style="color: #d1b70a;">${str}</span>`);
          this.error = "";
        }
        catch(exception) {
          this.error = exception.message;
        }
      }
      else{
        this.error = "";
      }
        
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
  color: #fefefe;
  margin-top: 0 auto;    
}

body{
  background-color: #273a47;
  padding: 10px;
  padding-bottom: 0;
}

input{
  display: block;
  margin: 0 auto;
  width: 80%;
}

h1{
  margin: 20px;
}

</style>
