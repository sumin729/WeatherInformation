<template>
  <div>
    <ul class="city-selector">
      <li
        @click="selectCity(city)"
        :class="{ isSelected: city.selected }"
        v-for="city in cities"
        :key="city.code"
      >
        {{ city.label }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "CitySelector",
  data() {
    return {
      cities: [
        { code: "Seoul", label: "서울", selected: false },
        { code: "Berlin", label: "베를린", selected: false },
        { code: "Chicago", label: "시카고", selected: false },
        { code: "Dubai", label: "두바이", selected: false },
        { code: "Hong Kong", label: "홍콩", selected: false },
        { code: "London", label: "런던", selected: false },
        { code: "Moscow", label: "모스코바", selected: false },
        { code: "New York", label: "뉴욕", selected: false },
        { code: "Paris", label: "파리", selected: false },
        { code: "Tokyo", label: "도쿄", selected: false },
      ],
    };
  },
  methods: {
    selectCity(city) {
      city.selected = !city.selected; //반댓값 넣으면 토글 버튼 구현됨.
      this.$emit("selectCity", city);
    },
  },
};
</script>

<style scoped>
.city-selector {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
}
.city-selector li {
  display: flex;
  justify-content: center;
  align-items: center;
  border: 0.05em solid #efefef;
  padding: 0.3em;
  cursor: pointer;
  padding: 0.8em;
  font-size: 17px;
}
.isSelected {
  background: dodgerblue;
  color: #fff;
}
</style>
