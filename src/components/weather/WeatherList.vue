<template>
  <div>
    <ul class="weather-list">
      <WeatherItem
        v-for="weather in WeatherList"
        :key="weather.code"
        :weather="weather"
      />
    </ul>
  </div>
</template>

<script>
import WeatherItem from "./WeatherItem.vue";
export default {
  name: "WeatherList",
  components: {
    WeatherItem,
  },
  props: {
    WeatherList: Array,
  },
};
</script>

<style scoped>
.weather-list {
  margin-top: 1em;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
</style>
