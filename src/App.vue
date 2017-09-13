<template>
  <div id="app">
    <div id="infomation">
      <div id="current-weather">
        <current-weather></current-weather>
      </div>
      <div id="forecast"></div>
    </div>
    <div id="map"></div>
  </div>
</template>

<script>
import CurrentWeather from './components/CurrentWeather'
export default {
  name: 'app',
  components: {
    CurrentWeather
  }
}
</script>

<style>
  body {
    background-color:#fafafa;
  }
  #app {
    position: absolute;
    top:50%;
    left:50%;
    width:1000px;
    height:600px;
    margin-top:-300px;
    margin-left:-500px;
    border-radius:3px;
    background-color:#444;
    box-shadow: 0px 2px 2px 2px rgba(0,0,0,0.3);
    overflow:hidden;
  }
  #app:after {
    content:'';
    display:block;
    clear: both;
  }
  #app > #infomation {
    float: left;
    width:600px;
  }
  #app > #infomation > #current-weather {
    height:180px;
    margin-top:20px;
  }
  #app > #infomation > #forecast {
    background-color:red;
    height: 400px;
  }
  #app > #map {
    float: right;
    width:400px;
    height: 600px;
    background-color:green;
  }
</style>
