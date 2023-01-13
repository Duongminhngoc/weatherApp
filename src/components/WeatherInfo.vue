<template>
  <div class="weatherInfo">
    <h2>{{ weather?.location?.name }}</h2>
    <p>{{ weather?.current?.condition?.text }}</p>
    <img :src="weather?.current?.condition?.icon" alt="icon" />
    <h1>{{ weather?.current?.temp_c }}&deg;C</h1>
  </div>
</template>

<script>
export default {
  name: "WeatherInfo",
  props: {
    msg: String,
    city: String,
  },
  data() {
    return {
      api_key: "4c4c38dfff5b482790c92832230601",
      url_base: "http://api.weatherapi.com/v1/current.json",
      query: "",
      weather: {},
      darkmode: false,
      weatherlist: [],
    };
  },
  methods: {
    fetchWeather() {
      fetch(`${this.url_base}?key=${this.api_key}&q=${this.city}&aqi=no`)
        .then((response) => {
          return response.json();
        })
        .then(this.weatherResult);
    },
    weatherResult(result) {
      this.weather = result;
    },
  },
  created() {
    this.fetchWeather();
  },
};
</script>

<style scoped>
.weatherInfo {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: white 1px solid;
  color: #fff;
  border-radius: 5px;
  padding: 10px;
  width: 250px;
  height: 200px;
  margin: 5px;
}
</style>
