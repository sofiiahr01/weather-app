<script>
export default {
  data() {
    return {
      city: "",
    };
  },
  computed: {
    cityName() {
      return "<" + this.city + ">";
    },
  },
  methods: {
    getWeather() {
      if (this.city.trim().length < 2) {
        this.error = "Название должно содержать более одного символа :)";
        return false;
      }
      this.error + "";
    },
  },
};
</script>

<template>
  <div class="wrapper">
    <h1>Погодное приложение</h1>
    <p>Узнать погоду в {{ city === "" ? "вашем городе" : cityName }}</p>
    <input type="text" v-model="city" placeholder="Введите город" />
    <button v-if="city !== ''" @click="getWeather()">Показать погоду</button>
    <button disabled v-else>Введите город</button>
    <p class="error">{{ error }}</p>
  </div>
</template>

<style scoped>
.error {
  color: red;
}

.wrapper {
  width: 900px;
  height: 500px;
  border-radius: 50px;
  padding: 20px;
  background: #1f0f24;
  text-align: center;
  color: white;
}

.wrapper h1 {
  margin-top: 20px;
}

.wapper p {
  margin-top: 20px;
}

.wrapper input {
  margin-top: 30px;
  background: transparent;
  border: 0;
  border-bottom: 2px solid #110813;
  color: #fcfcfc;
  font-size: 14px;
  padding: 5px 8px;
  outline: none;
}

.wrapper input:focus {
  border-bottom-color: #6e2d7d;
}

.wrapper button {
  background-color: #e3bc6b;
  color: #fff;
  border-radius: 10px;
  border: 2px solid #b99935;
  padding: 10px 15px;
  margin-left: 20px;
  cursor: pointer;
  transition: transform 500ms ease;
}

.wrapper button:disabled {
  background-color: #b68e3e;
  cursor: not-allowed;
}

.wrapper button:hover {
  transform: scale(1.1) translateY(-5px);
}
</style>
