<template>
  <div class="weather-wrapper">
    <ContentHeader />
    <CitySelector @selectCity="selectCity" />
    <WeatherList :WeatherList="WeatherList" />
  </div>
</template>

<script>
import weatherMixin from "@/mixins/weatherMixin";
import ContentHeader from "./ContentHeader";
import CitySelector from "./CitySelector.vue";
import WeatherList from "./WeatherList.vue";
export default {
  name: "WeatherContent",
  components: {
    ContentHeader,
    CitySelector,
    WeatherList,
  },
  mixins: [weatherMixin],
  data() {
    return {
      WeatherList: [],
    };
  },
  methods: {
    async selectCity(city) {
      if (city.selected) {
        const weather = await this.getWeatherInfo(city);
        console.log(weather, "weather");
        this.WeatherList.push(weather);
      } else {
        const index = this.WeatherList.findIndex(
          //현재 배열에서 조건에 맞는 값을 찾아줌
          (weather) => weather.code === city.code
        );
        this.WeatherList.splice(index, 1);
      }
    },
  },
};
</script>

<style></style>
