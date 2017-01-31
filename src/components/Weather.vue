<template>
  <div class="weather">
    <div class="location">{{location}}</div>
    <div class="date">{{date}}</div>
    <div class="description">{{description}}</div>
    <div class="current">
      <div class="visual">
        <div class="cloud"></div>
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
      <div class="low-temp">{{forecast.low-temp}}</div>
      <div class="high-temp">{{forecast.high-temp}}</div>

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
        {'date': 'Monday', 'icon': 'cloud', 'low-temp': 14, 'high-temp': 23},
        {'date': 'Tuesday', 'icon': 'sun', 'low-temp': 12, 'high-temp': 21},
        {'date': 'Wednesday', 'icon': 'sun-cloud', 'low-temp': 15, 'high-temp': 24},
        {'date': 'Thursday', 'icon': 'cloud', 'low-temp': 11, 'high-temp': 24},
        {'date': 'Friday', 'icon': 'raining', 'low-temp': 12, 'high-temp': 27},
        {'date': 'Saturday', 'icon': 'cloud', 'low-temp': 14, 'high-temp': 26},
        {'date': 'Sunday', 'icon': 'sun', 'low-temp': 16, 'high-temp': 23}
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
    width: 40%;
  }
  .text {
    width: 50%;
    float: right;

  }

  .forecast-dat {
    display: inline-block;
  }
</style>
