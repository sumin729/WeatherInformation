<template>
  <li class="weather-item">
    <h3>
      {{ weather.label }}
    </h3>
    <p class="temperature">{{ weather.temperature }}&deg;c</p>
    <p class="info">
      <img :src="weather.icon" alt="any" />
      <span>습도 {{ weather.humidity }}</span>
      <span>바람 {{ weather.wind }}m/s</span>
    </p>
  </li>
</template>

<script>
export default {
  name: "WeatherItem",
  props: {
    weather: {
      type: Object,
      default() {
        //오브젝트나 배열일 경우 메서드 형태로 선언.
        return {
          label: "서울",
          code: "Seoul",
          temperature: 20,
          humidity: 15,
          wind: 1.5,
        };
      },
    },
  },
};
</script>

<style scoped>
.weather-item {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 1px solid #efefef;
  padding: 2em;
}
.weather-item h3 {
  font-size: 18px;
  color: #333;
  font-weight:lighters;
}
.temperature {
  font-size: 26px;
}
.info {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 14px;
}
.info * {
  margin-right: 0.3em;
}
</style>
