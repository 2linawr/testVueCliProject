<template>
  <HelloWorld :msg="data_2"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
const data=[{
  id:'1',
  namecity:'Moscow',
  cech:[
    {namecech:'NameCech1',
    mans:['Ivanov','Petrov','Sidorov']},
     {namecech:'NameCech2',
    mans:['Ivanov2','Petrov2','Sidorov2']}]
},
{
  id:'2',
  namecity:'Mosco2',
  cech:[
    {namecech:'NameCech3',
    mans:['Ivanov3','Petrov3','Sidorov3']},
     {namecech:'NameCech4',
    mans:['Ivanov4','Petrov4','Sidorov4']}]
},
{
  id:'3',
  namecity:'Mosco3',
  cech:[
    {namecech:'NameCech5',
    mans:['Ivanov5','Petrov5','Sidorov5']},
     {namecech:'NameCech6',
    mans:['Ivanov6','Petrov6','Sidorov6']}]
}
]
export default {
  name: 'App',
 data(){
  return{
    data_2:data
  }
 },
  components: {
    HelloWorld
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
</style>
