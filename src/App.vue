<template>
  <div id="Travelapp">
    <div id = "Header">
        <a href="">Home</a>
        <a href="">About</a>
    </div>
    <div id = "Descriptions">
      <ul>
        <li v-for="d in desc" :key="d.header">
           {{d.header}}<br>
           <img src = "./assets/Pokhara.jpg"><br>
           {{d.description}}
        </li>
      </ul>

    </div>
  
  </div>
</template>

<script>
import descriptions from './Descriptions/Store.json';

export default {
  name: 'TravelApp',
  data(){
    return{
      desc:[]
    }
  },mounted(){
    this.desc = descriptions;
  },methods:{
    getUrl(imageLocation){
      var image = require.context('./assets/', false, /\.jpg$/);
      return image('./'+imageLocation)
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

#Header{
   padding: 30px;
  text-align: center;
  background: black;
  
  font-size: 30px;
}

a{
  padding: 20px;
  color: white;
}
</style>
