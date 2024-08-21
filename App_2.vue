<script>
import axios from 'axios'

export default {
  data() {
    return {
      city: '',
      error: '',
      info: null
    }
  },
  computed: {
    cityName() {
      return '<<' + this.city + '>>'
    },
    showTemp() {
      return 'Температура:' + this.info.main.temp
    },
    showFeelsLike() {
      return 'Ощущается как:' + this.info.main.feels_like
    },
    showMinTemp() {
      return 'Минимальная температура:' + this.info.main.temp_min
    },
    showMaxTemp() {
      return 'Максимальная температура:' + this.info.main.temp_max
    }
  },
  methods: {
    getWeather() {
      if (this.city.trim().length < 2) {
        this.error = 'Нужно более одного символа:'
        return false
      }

      this.error = ''

      axios
        .get(
          `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=efc594bcc73e81187ff2244668c370f9`
        )
        .then((res) => (this.info = res.data))
    }
  }
}
</script>

<template>
  <div className="wrapper">
    <h1>Погодное приложение</h1>
    <p>Узнать погоду в {{ city == '' ? 'вашем городе' : '<<' + city + '>>' }}</p>
    <input type="text" v-model="city" placeholder="Введите город" />
    <Button v-if="city != ''" @click="getWeather()">Получить погоду</Button>
    <Button disabled v-else>Введите город madafaka</Button>

    <p className="error">{{ error }}</p>

    <!-- <p v-show="info != null">{{ info.main.temp }}</p> -->

    <div v-if="info != null">
      <p>{{showTemp}}</p>
      <p>{{showFeelsLike}}</p>
      <p>{{showMinTemp}}</p>
      <p>{{showMaxTemp}}</p>
    </div>
  </div>
</template>

<style scoped>
.error {
  color: rgb(255, 68, 68);
}

.wrapper {
  width: 700px;
  height: 300px;
  border-radius: 50px;
  background: rgb(196, 255, 224);
  background: linear-gradient(
    90deg,
    rgba(196, 255, 224, 1) 0%,
    rgba(122, 236, 255, 1) 46%,
    rgba(115, 255, 152, 1) 100%
  );

  padding: 20px;
  text-align: center;
  color: #fff;
}

.wrapper h1 {
  margin-top: 30px;
}

.wrapper p {
  margin-top: 15px;
}

.wrapper input {
  margin-right: 20px;
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
  border-bottom-color: #4399ff;
}

.wrapper button:disabled {
  background-color: #a6a6a6;
  border: 2px solid #a6a6a6;
  cursor: not-allowed;
}

.wrapper button {
  background: #f9c132;
  padding: 10px 15px;
  color: #fff;
  cursor: pointer;
  border-radius: 20px;
  transition: transform 500ms ease;
  border: 2px solid #f9c132;
}

.wrapper button:hover {
  transform: scale(1.1) translateY(-5px);
}
</style>
