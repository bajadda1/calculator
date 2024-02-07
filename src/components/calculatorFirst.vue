<template>
  <div class="w-full h-screen bg-[#220732] flex flex-row justify-center p-4 sm:p-0" id="container">
    <div class="w-full sm:w-1/2 md:w-[45%] lg:w-1/3 h-full flex flex-col justify-center items-center gap-4">
      <!--      first div **************************************************-->
      <div class="w-full h-[10%] flex flex-row justify-between">
        <div class="w-1/6 h-full flex flex-col items-start justify-center">
          <p class="text-4xl font-bold text-yellow-500  my-auto">
            calc
          </p>
        </div>
        <div class="w-1/3 h-full flex flex-row justify-between">
          <div class="w-[30%] h-full">
            <div class="w-full h-full flex flex-col items-center">
              <p class="text-xs font-bold text-yellow-400  my-auto">
                THEME
              </p>
            </div>
          </div>
          <div class="w-[60%] h-full">
            <div class="w-full h-full flex flex-row justify-between">
              <div class="w-1/5 h-full flex flex-col items-center">
                <div>
                  <label class="font-bold text-xs text-yellow-400" for="one">1</label>
                </div>
                <div>

                  <input type="radio" name="radio" id="one" checked value="one" v-model="selectedOption" >
                </div>

              </div>
              <div class="w-1/5 h-full flex flex-col items-center">
                <div>
                  <label class="font-bold text-xs text-yellow-400"  for="two">2</label>
                </div>
                <div>
                  <input type="radio" name="radio" value="two" v-model="selectedOption" id="two">
                </div>

              </div>
              <div class="w-1/5 h-full flex flex-col items-center">
                <div>
                  <label class="font-bold text-xs text-yellow-400" for="three">3</label>
                </div>
                <div>
                  <input type="radio" name="radio" value="three" v-model="selectedOption" id="three">
                </div>

              </div>
            </div>
          </div>
        </div>

      </div>
      <!--      second div **************************************************-->

      <div class="bg-[#4A0E6E] w-full h-[15%] rounded rounded-md shadow shadow-sm p-4">
        <div class="w-full h-full">
          <input type="text"
                 v-model="inputField"
                 class="w-full h-full outline-none bg-transparent text-2xl text-yellow-400 font-bold text-right"
          id="INPUT">
        </div>

      </div>
      <!--      third div **************************************************-->

      <div class="bg-[#4A0E6E] w-full h-[50%] sm:h-[60%] p-4 rounded rounded-md shadow shadow-sm">
        <div class="w-full h-full flex flex-col space-y-4 sm:space-y-4">
          <div class="w-full flex-1 sm:flex-1 flex justify-between">
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">7</p>
            </div>
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">8</p>
            </div>
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">9</p>
            </div>
            <div class="w-1/5 sm:w-1/6  h-full bg-purple-800 rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
              @click="deleteNumberOperator">DEL</p>
            </div>

          </div>
          <div class="w-full flex-1 sm:flex-1 flex justify-between">
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">4</p>
            </div>
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">5</p>
            </div>
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">6</p>
            </div>
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">+</p>
            </div>

          </div>
          <div class="w-full flex-1 sm:flex-1 flex justify-between">
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">1</p>
            </div>
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">2</p>
            </div>
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">3</p>
            </div>
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">-</p>
            </div>

          </div>
          <div class="w-full flex-1 sm:flex-1 flex justify-between">
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">.</p>
            </div>
            <div class="w-1/5 sm:w-1/6  h-full bg-black rounded rounded-md shadow shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">0</p>
            </div>
            <div class="w-1/5 sm:w-1/6  h-full bg-black  rounded-md  shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">/</p>
            </div>
            <div class="w-1/5 sm:w-1/6  h-full bg-black  rounded-md  shadow-sm border-purple-600 border-b-4
            flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
                 @click="pushNumberOperator">*</p>
<!--              &times;-->
            </div>

          </div>
          <div class="w-full flex-1 sm:flex-1 flex justify-between space-x-14">
            <div class="flex-1 h-full bg-black  rounded-md  shadow-sm border-purple-600 border-b-4
flex flex-row items-center justify-center cursor-pointer">
              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
              @click="resetInput">RESET</p>
            </div>
            <div class="flex-1 h-full bg-cyan-500  rounded-md  shadow-sm border-purple-600 border-b-4
flex flex-row items-center justify-center cursor-pointer">

              <p class="font-bold text-2xl text-yellow-500 w-full h-full flex items-center justify-center select-none"
              @click="finalResult">=</p>

            </div>
          </div>
        </div>

      </div>

    </div>

  </div>
</template>

<script>
export default {
  name: "calculatorFirst",
  data() {
    return {
      inputField:"",
      selectedOption:null,
    };

  },

  methods: {
    pushNumberOperator(e) {

      this.inputField += e.target.innerHTML;
      let n=this.inputField.length;
      let i=n-2;
      //avoid user to start with operator
      const op=["+","-","/","*"];
      if(op.includes(this.inputField.charAt(0))) {
        this.inputField="0"+this.inputField;
      }
      //avoid two operators successive
      if((op.includes(this.inputField.charAt(i))) && (op.includes(this.inputField.charAt(i+1)))){
        this.inputField=this.inputField.substring(0,i)+this.inputField.substring(i+1);
        console.log("yes");
      }
    },
    deleteNumberOperator(){
      let str=this.inputField;
      this.inputField=str.slice(0,-1);
    },
    resetInput(){
     this.inputField="";
    },
    calculate(val1,val2,operator){
      let result=0;
      switch (operator){
        case "+":
          result=parseFloat(val1)+parseFloat(val2);
          break;
        case "-":
          result=parseFloat(val1)-parseFloat(val2);
          break;
        case "/":
          if(val2!=="0")
            result=parseFloat(val1)/parseFloat(val2);
          else
            result=null;
          break;
        case "*":
          result=parseFloat(val1)*parseFloat(val2);
          break;
        default:
          console.log("Empty operator received.");
      }
      return result;
    },
    stringToNumber(list){
      let n=list.length;
      const op=["+","-","/","*"];
      if(n!==0){
        for(let i=0;i<n;i++){
          if(!op.includes(list[i])){
            list[i]=parseFloat(list[i]);
          }
        }
      }
      return list;
    },
    multiplyDivisionFirst(list){
      let res=0;
      let n=list.length;
      list=this.stringToNumber(list);
      for(let i=0;i<n-1;i++){
        if((list[i]==="*") || (list[i]==="/")){
          res=this.calculate(list[i-1],list[i+1],list[i]);
          //calculate result and reduce the length of list 3 cases replaced with one
          list.splice(i-1,3,res);
        }
        res=0;
      }
    },
    additionSubstractionList(list){
      let res=0;
      //start with multiplacation and division
      this.multiplyDivisionFirst(list);
      let n=list.length;
      while (n>=3){
        res=this.calculate(list[0],list[2],list[1]);
        list.splice(0,3,res);
        n=n-2;
        res=0;
        console.log(list);
      }

    },
    accumulate(list){
      const op=["+","-","/","*"];
      let newlist=[];
      let el="";
      let n=list.length;
      for (let i=0;i<n;i++){
        if(!op.includes(list[i])){
          el+=list[i];
        }
        else{
          newlist.push(el);
          el="";
          newlist.push(list[i]);
        }
      }
      newlist.push(el);
      return newlist;
    },
    finalResult(){
      const op=["+","-","/","*"];
      let n=this.inputField.length;
      if(n!==0){
        
        if(op.includes(this.inputField.charAt(n-1))){
          this.inputField=this.inputField.slice(0,-1);
        }
      }
      console.log(this.inputField);
      console.log(this.inputField.split(""));
      let list=this.accumulate(this.inputField.split(""));
      console.log(list);
      this.additionSubstractionList(list);
      console.log(list);
      this.inputField=list.join("");
    },

  },
  watch:{
    selectedOption(value){
      let container=document.getElementById("container");
      let firstDiv=document.querySelector("#container >div >div:nth-child(2)");
      let secondDiv=document.querySelector("#container >div >div:nth-child(3)");
      let INPUT=document.querySelector("#INPUT");
      switch (value){
        case "one":
          container.style.backgroundColor="#220732";
          firstDiv.style.backgroundColor="#4A0E6E";
          secondDiv.style.backgroundColor="#4A0E6E";
          INPUT.style.color="#ece007";
          break;
        case "two":
          container.style.backgroundColor="#000000";
          firstDiv.style.backgroundColor="#fcece1";
          secondDiv.style.backgroundColor="#fcece1";
          INPUT.style.color="black";
          break;
        case "three":
          container.style.backgroundColor="#590404";
          firstDiv.style.backgroundColor="#ffffff";
          secondDiv.style.backgroundColor="#ffffff";
          INPUT.style.color="#000000";
          break;
        default:
          container.style.backgroundColor="#220732";
      }
    }
  },


}
</script>

<style scoped>
#one,#two,#three{
  width: 15px;
  height: 15px;
  border: 2px solid red;
  border-radius: 50%;
  background-color: #095b5b;
}
</style>