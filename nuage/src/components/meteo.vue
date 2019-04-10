<template>
<div>
  <span class="input">
    <input type="text" class="form-control" v-model="city" placeholder="Enter your City Here">
    <span></span>
  </span>
  <button class="form-button" type="submit" name="button" @click="getApi(city)">GO</button>
    <b-container class="list-group"></b>
      <p class="list-group-item">{{hub}}</p>
      <p class="list-group-item">{{degree}}</p>
      <p class="list-group-item">{{crow}}</p>
      <p class="list-group-item">{{speed}}</p>
      <p class="list-group-item">{{date}}</p>
    </b-container>
</div>
<div>
  <b-alert show variant="success">
    <h4 class="alert-heading">Well done!</h4>
    <p>
      Aww yeah, you successfully read this important alert message. This example text is going to
      run a bit longer so that you can see how spacing within an alert works with this kind of
      content.
    </p>
    <hr>
    <p class="mb-0">
      Whenever you need to, be sure to use margin utilities to keep things nice and tidy.
    </p>
  </b-alert>
</div>
<div>
  <b-card
    title="Card Title"
    img-src="https://picsum.photos/600/300/?image=25"
    img-alt="Image"
    img-top
    tag="article"
    style="max-width: 20rem;"
    class="mb-2"
  >
    <b-card-text>
      Some quick example text to build on the card title and make up the bulk of the card's content.
    </b-card-text>

    <b-button href="#" variant="primary">Go somewhere</b-button>
  </b-card>
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
        this.crow = response.data.city.population;
        this.speed = response.data.list[0].wind.speed;
        this.date = response.data.list[0].dt_txt;

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


    list-group{
     position: inherit;
     top: 2px;
     padding-left: 8px;
   }

</style>
