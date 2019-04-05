<!-- <div class="">
    <h1>Ta-Met-Tes-Haut</h1>
</div> -->


  <div class="container">
    <div class="col-md-3"></div>
    <div class="col-md-6">
      <div class="form-group">
        <input type="text" class="form-control" v-model="city" placeholder="Enter your City Here">
      </div>
      <button type="submit" v-on:click='getData' class="btn btn-default">GO</button>

      <div class="col-md-6">
        <div class="panel panel-default">
          <div class="panel-body">
            <p>
              <!-- {{data | json }} -->
            </p>
          </div>
          <ul class="list-group">
            <img src="http://openweathermap.org/img/w/{{data.weather[0].icon}}.png" alt="">
            <li class="list-group-item">Weather{{data.weather[0].main}}</li>
            <li class="list-group-item">Description{{data.weather[0].Description}}</li>
            <li class="list-group-item">Max T°{{data.main.temp_max}}</li>
            <li class="list-group-item">Min T°{{data.main.temp_min}}</li>
            <li class="list-group-item">Humidity{{data.main.humidity}}</li>
          </ul>

        </div>

      </div>
    </div>

  </div>


<script>
export default {}
name:'meteo',
},
data () {
  return {
    getData:"",
  }
}
</script>








<style lang="css" scoped>
</style>
