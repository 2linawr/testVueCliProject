<template>
  <div class="hello">
<div id="content">
  <div class="select-wrapper">
    <select id="select_1" v-on:click="handleClick()" >
      <option v-for="(fruit, index) in msg" :key="index">{{ fruit.namecity }}</option>
    </select>

    <div class="select-arrow-1"></div>
  </div>
  <div class="select-wrapper">
    <div class="select-arrow-2"></div>
    <select id="select_2" v-on:click="handleClick_2()" >
         <option v-for="(fruit, index) in message" :key="index">{{ fruit.namecech }}</option>
    </select>
  </div>
  <div class="select-wrapper">
    <div class="select-arrow-3"></div>
    <div class="select-arrow-3"></div>
    <select id="select_3" >
        <option v-for="(fruit, index) in mans" :key="index">{{ fruit }}</option>
    </select>
  </div>
  <input id="smena" class="smena" :value='smena_2' >
  <button class="bubbly-button" v-on:click="ClickButton()">Сохранить куки</button>
  </div>

  </div>
</template>
<script>
export default {
  name: 'HelloWorld',
 data() {
let smena = "";
let currentD = new Date();
let startHappyHourD = new Date();
startHappyHourD.setHours(8,0,0,0);
let endHappyHourD = new Date();
endHappyHourD.setHours(20,0,0,0); 
 try{
if(currentD >= startHappyHourD && currentD < endHappyHourD ){
smena="День";
}else{
smena="Ночь";
}
 }
 catch(err){
  console.log(err);
 }
   return {
      message: this.msg[0].cech,
      mans:this.msg[0].cech[0].mans,
      smena_2:smena
};
  },
  props:['msg'],
  methods: {
    handleClick() {
      let select_1=document.getElementById('select_1').value;

try {
      for(let i=0;i<=this.msg.length;i++){
        if(this.msg[i].namecity==select_1){
        this.message=this.msg[i].cech;  
        }
      
      }} catch (err) {

  // обработка ошибки

}
    },
     handleClick_2() {
      let select_1=document.getElementById('select_2').value;

try {
      for(let i=0;i<=this.msg.length;i++){
        for(let j=0;j<=this.msg.length;j++){
        if(this.msg[i].cech[j].namecech==select_1){
        this.mans=this.msg[i].cech[j].mans;  
        }
        }
      }} catch (err) {

  // обработка ошибки

}
    },
     ClickButton() {
     let select_1=document.getElementById('select_1').value;
      let select_2=document.getElementById('select_2').value;
      let select_3=document.getElementById('select_3').value;
      let select_4=document.getElementById('smena').value;
      document.cookie = "City="+select_1;
        document.cookie = "Cech="+select_2;
        document.cookie = "Mans="+select_3;
        document.cookie = "Smena="+select_4;
        console.log(document.cookie);
  
}
    },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  color: #6C7231;
  font-family: Helvetica;
  font-weight: bold;
}

.bubbly-button {
  font-family: "Helvetica", "Arial", sans-serif;
  display: inline-block;
  font-size: 1em;
  padding: 1em 2em;
  margin-top: 100px;
  margin-bottom: 60px;
  -webkit-appearance: none;
  appearance: none;
  background-color: #ff0081;
  color: #fff;
  border-radius: 4px;
  border: none;
  cursor: pointer;
  position: relative;
  transition: transform ease-in 0.1s, box-shadow ease-in 0.25s;
  box-shadow: 0 2px 25px rgba(255, 0, 130, 0.5);
}
.bubbly-button:focus {
  outline: 0;
}
.bubbly-button:before, .bubbly-button:after {
  position: absolute;
  content: "";
  display: block;
  width: 140%;
  height: 100%;
  left: -20%;
  z-index: -1000;
  transition: all ease-in-out 0.5s;
  background-repeat: no-repeat;
}
.bubbly-button:before {
  display: none;
  top: -75%;
  background-image: radial-gradient(circle, #ff0081 20%, transparent 20%), radial-gradient(circle, transparent 20%, #ff0081 20%, transparent 30%), radial-gradient(circle, #ff0081 20%, transparent 20%), radial-gradient(circle, #ff0081 20%, transparent 20%), radial-gradient(circle, transparent 10%, #ff0081 15%, transparent 20%), radial-gradient(circle, #ff0081 20%, transparent 20%), radial-gradient(circle, #ff0081 20%, transparent 20%), radial-gradient(circle, #ff0081 20%, transparent 20%), radial-gradient(circle, #ff0081 20%, transparent 20%);
  background-size: 10% 10%, 20% 20%, 15% 15%, 20% 20%, 18% 18%, 10% 10%, 15% 15%, 10% 10%, 18% 18%;
}
.bubbly-button:after {
  display: none;
  bottom: -75%;
  background-image: radial-gradient(circle, #ff0081 20%, transparent 20%), radial-gradient(circle, #ff0081 20%, transparent 20%), radial-gradient(circle, transparent 10%, #ff0081 15%, transparent 20%), radial-gradient(circle, #ff0081 20%, transparent 20%), radial-gradient(circle, #ff0081 20%, transparent 20%), radial-gradient(circle, #ff0081 20%, transparent 20%), radial-gradient(circle, #ff0081 20%, transparent 20%);
  background-size: 15% 15%, 20% 20%, 18% 18%, 20% 20%, 15% 15%, 10% 10%, 20% 20%;
}
.bubbly-button:active {
  transform: scale(0.9);
  background-color: #e60074;
  box-shadow: 0 2px 25px rgba(255, 0, 130, 0.2);
}
.bubbly-button.animate:before {
  display: block;
  animation: topBubbles ease-in-out 0.75s forwards;
}
.bubbly-button.animate:after {
  display: block;
  animation: bottomBubbles ease-in-out 0.75s forwards;
}

@keyframes topBubbles {
  0% {
    background-position: 5% 90%, 10% 90%, 10% 90%, 15% 90%, 25% 90%, 25% 90%, 40% 90%, 55% 90%, 70% 90%;
  }
  50% {
    background-position: 0% 80%, 0% 20%, 10% 40%, 20% 0%, 30% 30%, 22% 50%, 50% 50%, 65% 20%, 90% 30%;
  }
  100% {
    background-position: 0% 70%, 0% 10%, 10% 30%, 20% -10%, 30% 20%, 22% 40%, 50% 40%, 65% 10%, 90% 20%;
    background-size: 0% 0%, 0% 0%, 0% 0%, 0% 0%, 0% 0%, 0% 0%;
  }
}
@keyframes bottomBubbles {
  0% {
    background-position: 10% -10%, 30% 10%, 55% -10%, 70% -10%, 85% -10%, 70% -10%, 70% 0%;
  }
  50% {
    background-position: 0% 80%, 20% 80%, 45% 60%, 60% 100%, 75% 70%, 95% 60%, 105% 0%;
  }
  100% {
    background-position: 0% 90%, 20% 90%, 45% 70%, 60% 110%, 75% 80%, 95% 70%, 110% 10%;
    background-size: 0% 0%, 0% 0%, 0% 0%, 0% 0%, 0% 0%, 0% 0%;
  }
}

#content {
  width: 300px;
  margin: 20px auto;
  padding: 10px;
  border: 1px dotted gray;
}
.smena{
  position: relative;
  width: 300px;
  margin: 20px 0;
  border: 1px solid #6C7231;
  border-radius: 3px;
  height:28px;

}
.select-wrapper {
  position: relative;
  width: 300px;
  margin: 20px 0;
  border: 1px solid #6C7231;
  border-radius: 3px;
}

.select-wrapper:hover {
  box-shadow: 0px 0px 3px gray;
}

.select-wrapper select {
  width: 300px;
  height: 28px;
  padding: 0 20px 0 7px;
  background: transparent;
  border: 0;
  appearance: none;            /* remove arrow        */
  -webkit-appearance: none;    /* remove arrow Chrome */
  -moz-appearance: none;       /* remove arrow FF     */
}
.select-wrapper select::-ms-expand{
    display: none;             /* remove arrow IE     */
}

/* 
 * Style #1 
 * todo: try to change arrow DIV to pseudo :after
*/

.select-arrow-1 {
  position: absolute;
  z-index: -9999;
  right: 4px;
  bottom: 5px;
  border: 8px solid;
  border-color: white white #6C7231 white;
  border-right: 0;
}

/* Style #2 */

.select-arrow-2 {
  position: absolute;
  z-index: -9999;
  right: 4px;
  bottom: 5px;
  border: 8px solid;
  border-color: white white #6C7231 white;
  border-right: 0;
}

/* Style #3 */

.select-arrow-3 {
  position: absolute;
  z-index: -9999;
  right: 4px;
  bottom: 5px;
  border: 8px solid;
  border-color: white white #6C7231 white;
  border-right: 0;
}

</style>
