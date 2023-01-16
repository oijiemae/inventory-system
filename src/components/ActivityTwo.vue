<script>
export default {
  data() {
      return {
          input: '',
          output:'',
          calculated:false
      }
  },
  methods: {
      clear() {
          this.input=''
          this.output=''
      },
      cancel(){
          //this.input = this.input.slice(0, -1);
          const arr = this.input.split('')
          arr.pop()
          this.input = arr.join('')
      },
      enter(keys){
          if(!this.calculated){
              this.input +=keys
          }
          else{
              this.calculated = false
              this.input=''
              this.output=''
              this.input +=keys                
          }
      },
      equal(){
          if(this.input.includes('%')){
              const arr = this.input.split('')
              const newArr = []
              for(let i=0;i<arr.length;i++){
                  if(arr[i]!='%'){
                      newArr.push(arr[i])
                  }
                  else{
                      newArr.push('/100')
                  }
              }
              this.input = newArr.join('')
              console.log(newArr)
          }
          console.log(this.input)
          this.output = eval(this.input)
          this.calculated = true
      }
  },
  
}
</script>

<template>
  <div class="calculator">
      <div class="display">
          <div class="input"><span></span>
              {{input}}
          </div>
          <div class="output"><span></span>
              {{output}}
          </div>
      </div>
      <div class="row-1">
          <div class="button keys" @click="clear">AC</div>
          <div class="button keys" @click="cancel">+/-</div>
          <div class="button keys" @click="enter('%')">%</div>
          <div class="button operator" @click="enter('/')">÷</div>
      </div>
      <div class="row-2">
          <div class="button" @click="enter(7)">7</div>
          <div class="button" @click="enter(8)">8</div>
          <div class="button" @click="enter(9)">9</div>
          <div class="button operator" @click="enter('*')">x</div>
      </div>
      <div class="row-3">
          <div class="button" @click="enter(4)">4</div>
          <div class="button" @click="enter(5)">5</div>
          <div class="button" @click="enter(6)">6</div>
          <div class="button operator" @click="enter('-')">-</div>
      </div>
      <div class="row-4">
          <div class="button" @click="enter(1)">1</div>
          <div class="button" @click="enter(2)">2</div>
          <div class="button" @click="enter(3)">3</div>
          <div class="button operator" @click="enter('+')">+</div>
      </div>
      <div class="row-5">
          <div class="button" @click="cancel">&#8634;</div>  
          <div class="button" @click="enter('0')">0</div>
          <div class="button operator" @click="enter('.')">.</div>
          <div class="button operator" @click="equal">=</div>
      </div>
  </div>
  
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: sans-serif;
}
.app {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.calculator{
  min-height: 640px;
  max-width: 375px;
  font-size: 2rem;
  width:100%;
  height:30rem;
  margin:auto;
  margin-top: 2rem;
  margin-bottom: 3rem;
  background-color: rgb white;
  border: 4px solid rgb(241, 241, 234);
  border-radius: 5rem;
  -webkit-border-radius: 2.4rem;
  -moz-border-radius: 0.4rem;
  -ms-border-radius: 0.4rem;
  -o-border-radius: 0.4rem;
  -webkit-box-shadow: 1rem 1rem 0.5rem rgb white;
  box-shadow: 0.1rem 0.1rem 0.5rem rgb lightgray;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;

}
.display{
  min-width: 20px;
  font-size:1.8rem;
  width:80%;
  height:6px;
  border: 1px solid rgb white;
  border-radius: 0.5rem;
  background-color: rgb white;
  margin: auto;
  text-align: right;
  flex: 10%;
  margin-top: 8.5rem;
}
.row-1,.row-2,.row-3,.row-4,.row-5{
  width:90%;
  height:auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin:auto;
  margin-top: 0.7rem;
  margin-bottom: 2.5%;
}
.row-1 .button{
  background-color: #f8f8f8;
}
.row-2 .button{
  background-color: #f8f8f8;
}
.row-3 .button{
  background-color: #f8f8f8;
}
.row-4 .button{
  background-color: #f8f8f8;
}
.row-5 .button{
  background-color: #f8f8f8;
}
.button{
  position: relative;
  width: 20%;
  max-block-size: 100%;
	cursor: pointer;
	display: block;
	height: 3rem;
	padding-top: 0.5%;
	border-radius: 0.5rem;
	transition: 0.2s;
	user-select: none;
  text-align: center;
  font-weight: 100%;
  font-size: 2rem;
}

.button.equal{
  width:30%;
}
.button:hover,.button.button.equal:hover{
  color: rgb white;
  -webkit-box-shadow: 0.3rem 0.3rem 0.5rem #000000;
  box-shadow: 0.3rem 0.3rem 0.5rem #000000;
}
.button:active,.button.button.equal:active{
  transform: translate(0.05rem,0.05rem);
  -moz-transform: translate(0.05rem,0.05rem);
  -webkit-transform: translate(0.05rem,0.05rem);
}
.button.reload{
  width: 20%;
}
.button.button.button.reload:active{
  transform: translate(0.05rem,0.05rem);
  -moz-transform: translate(0.05rem,0.05rem);
  -webkit-transform: translate(0.05rem,0.05rem);
}
.button:hover,.button.button.equal:hover{
  color: #000000;
  -webkit-box-shadow: 0.3rem 0.3rem 0.5rem #000000;
  box-shadow: 0.3rem 0.3rem 0.5rem #000000;
}
.input,output{
  min-width: 280px;
  width:100%;
  margin:auto 0;
}
.display .input{
  font-size: 1.60rem;
  margin-bottom: 0.5rem;
  color:#000000;
  font-size: 2rem;

}
.display .output {
  color: #000000;
  font-size: 4rem;
  font-weight: 700;
  width: 100%;
  max-width: 100%;
  overflow: auto;
}
.operator{
  color: #eb6666 ;
}
.keys {
  color: #0ff ;
}
</style>