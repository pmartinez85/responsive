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
        <div class="humidity">Humidity: {{humidity}}</div>
        <div class="wind">Wind: {{wind}}</div>
        <div class="pollen">Pollen: {{pollen}}</div>
      </div>
    </div>
    <div class="forecast">
    <div class="forecast-day" v-for="forecast in forecasts">
      <div class="date">{{forecast.date}}</div>
      <div></div>
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
      forecasts: []
    }
  },
  methods: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  .weather {
    width: 100%;
    padding:20px;
    box-shadow: 0 10px 40px  rga(0,0,0,0,2);
  }

  @media (min-width: 700px) {
    .weather {
      width: 700px;
    }

  }

  @media (min-width: 650px) {
    .location {
      font-size: 5am;
    }

    @media (max-width : 650px)


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
    width: 14.285%;
  }

  .forecast-day {
    display: inline-block;
    width: 14.285%;
  }
   .icon {
    background-repeat: no-repeat;
    background-size: contain;
    margin-left: auto;
    margin-right: auto;
  }

  .icon.cloudy .icon {
  background-image: url('../assets/cloudy.png');
  font-size: 2em;

  }
</style>
