<template>
  <div>
    <div class="location">{{ location }}</div>
    <div class="wheather">{{ weather }}</div>
    <div class="temp">{{ temp }}C</div>
  </div>
</template>
<script>
export default {
  name: 'current-weather',
  data () {
    return {
      location: '',
      weather: '',
      temp: '',
      lat: 37.566535,
      lon: 126.977969
    }
  },
  mounted () {
    this.axios.get('http://api.openweathermap.org/data/2.5/weather', {
      params: {
        lat: this.lat,
        lon: this.lon,
        APPID: '4af00da88b59b73f333a28245c40f5ce'
      }
    })
    .then(response => {
      let data = response.data
      console.log(data)
      this.location = data.name
      this.weather = data.weather[0].main
      this.temp = (data.main.temp - 273.15).toFixed(0)
    })
  }
}
</script>
<style>
  .location {
    text-align:center;
    font-size:40pt;
    color:white;
  }
  .wheather {
    text-align: center;
    font-size: 20pt;
    color:white;
  }
  .temp {
    text-align: center;
    font-size: 50pt;
    color:white;
  }
</style>
