<template>
  <div class="weather">
    <div class="header">
      <h1>Vue Weather Application</h1>
      <p>Built atop Vue & OpenWeatherMap</p>
      <select multiple class="select-city" v-model="selected">
        <option v-for="(city, index) in cities" :key="index" :value="city.key">
          {{ city.name }}
        </option>
      </select>
    </div>
    <div class="main">
      <WeatherInfo
        v-for="city in selected"
        :key="city"
        :city="city"
      ></WeatherInfo>
    </div>
  </div>
</template>

<script>
import WeatherInfo from "./WeatherInfo.vue";
export default {
  name: "WeatherApp",
  components: {
    WeatherInfo,
  },
  props: {
    msg: String,
  },
  data() {
    return {
      selected: [],
      cities: [
        { key: "Ha Noi", name: "Hà Nội" },
        { key: "Ha Tinh", name: "Hà Tĩnh" },
        { key: "Ky Anh", name: "Kỳ Anh" },
        { key: "Manila", name: "Manila" },
        { key: "Pasay", name: "Pasay" },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  color: rgb(218, 225, 231);
  margin-bottom: 30px;
}
.main {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin: 50px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.select-city {
  width: 200px;
  margin-top: 20px;
}
.select-city option {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 20px;
  padding: 5px;
}
</style>
