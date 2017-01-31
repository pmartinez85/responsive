<template>
  <div class="weather">
    <div class="location">{{location}}</div>
    <div class="date">{{date}}</div>
    <div class="description">{{description}}</div>
    <div class="current">
      <div class="visual">
        <div class="cloud">Cloud</div>
          <div class="temp">{{temp}}</div>
        <div class="scale">º</div>
      </div>
      <div class="text">
        <div class="precipitation">Precipitation: {{precipitation}}</div>
        <div class="humidity">humidity: {{humidity}}</div>
        <div class="wind">wind: {{wind}}</div>
        <div class="pollen">pollen: {{pollen}}</div>
      </div>
    </div>
    <div class="forecast">
    <div class="forecast-day" v-for="forecast in forecasts">
      <div class="date">{{forecast.date}}</div>
      <div class="icon">{{forecast.icon}}</div>
      <div class="lowtemp">{{forecast.lowtemp}}</div>
      <div class="hightemp">{{forecast.hightemp}}</div>

    </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'weather',
  data () {
    return {
      location: 'New York, NY',
      date: 'Tuesday, April 15th',
      description: ' Description  here',
      temp: 25,
      precipitation: '100%',
      humidity: 97,
      wind: '4mph SW',
      pollen: 36,
      forecasts: [
        {'date': 'Monday', 'icon': 'cloud', 'lowtemp': 14, 'hightemp': 23},
        {'date': 'Tuesday', 'icon': 'sun', 'lowtemp': 12, 'hightemp': 21},
        {'date': 'Wednesday', 'icon': 'sun-cloud', 'lowtemp': 15, 'hightemp': 24},
        {'date': 'Thursday', 'icon': 'cloud', 'lowtemp': 11, 'hightemp': 24},
        {'date': 'Friday', 'icon': 'raining', 'lowtemp': 12, 'hightemp': 27},
        {'date': 'Saturday', 'icon': 'cloud', 'lowtemp': 14, 'hightemp': 26},
        {'date': 'Sunday', 'icon': 'sun', 'lowtemp': 16, 'hightemp': 23}
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .weather {
    padding:20px;
  }
  .location {
    font-size: 3em;
  }
  date {
    font-size: 1.5em;
  }
  .description {
    font-size: 1.1em;
  }
  .current {
  overflow: auto;
  width: 100%;

  }
  .visual {
    float: left;
    width: 50%;
  }
  .text {
    width: 50%;
    float: right;

  }

  .forecast-day {
    display: inline-block;
    width: 14.285%,
  }
  .icon {
    background-repeat: no-repeat;
    background-size: contain;
  }

  .icon.cloudy {
  background-image: url('../assets/logo.png');
  font-size: 2em;

  }
</style>
