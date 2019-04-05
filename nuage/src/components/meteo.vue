<template>
<div>

  <span class="input">
    <input type="text" class="form-control" v-model="city" placeholder="Enter your City Here">
    <span></span>
  </span>
  <button class="form-button" type="submit" name="button" @click="getApi(city)">GO</button>
  <div>
    <p >{{hub}}</p>
    <p>{{degree}}</p>
    <p>{{crow}}</p>
    <p>{{speed}}</p>
    <p>{{date}}</p>


  </div>

</div>

</template>

<script>
export default {
  data() {
    return {
      city: '',
      hub: '',
      degree: '',
      crow: '',
      speed: '',
      date: '',
    }
  },
  methods: {
    getApi(city) {
      var happy = "https://api.openweathermap.org/data/2.5/forecast?q=" + city + "&units=metric&APPID=b5adeb2fa879be2ce6147b10c08e02c5";


      this.axios.get(happy).then((response) => {
        console.log(response.data);

        this.hub = response.data.city.name;
        console.log(this.hub);
        this.degree = response.data.list[0].main.temp;
        this.crow= response.data.city.population;
        this.speed= response.data.list[0].wind.speed;
        this.date= response.data.list[0][2² ²   ² ²].dt_txt;

      })

    }

  },
  props: {

  }
}
</script>

<style lang="css" scoped>

.form-button {
color: #fff !important;
text-transform: uppercase;
background: #2693e2;
padding: 20px;
border-radius: 5px;
display: inline-block;
border: none;
}

.form-button:hover {
background:rgb(23, 88, 233) ;
letter-spacing: 1px;
-webkit-box-shadow: 0px 10px 40px -50px rgba(99, 104, 222, 0.57);
-moz-box-shadow: 0px 5px 40px -10px rgba(102, 122, 228, 0.57);
box-shadow: 5px 40px -10px rgb(8, 18, 242);
transition: all 0.4s ease 0s;
}

.form-control {
  position:relative;
  font-size: 1.5em;
  padding: 10px;
  display: inline-block;
  border-radius: 9999em;
  }
  *:not(span) {
		position: relative;
		display: inherit;
		border-radius: inherit;
		margin: 0;
		border: none;
		outline: none;
		padding: 0 .325em;
		z-index: 1;
  }
  &:focus + span {
			opacity: 1;
			transform: scale(1);
		}


</style>
