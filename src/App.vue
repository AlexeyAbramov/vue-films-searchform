<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="header col">
          <h1 class="text-center">HOOKED</h1>
        </div>
      </div>
      <div class="row">
        <div class="search col text-center">
          <div class="field mt-4 text-center"><input type="text" /></div>
          <button class="btn btn-primary mt-4" @click="request">Search</button>
        </div>
        {{filmsData.Title}}
        {{filmsData.BoxOffice}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      key:'',
      filmsData:''
    }
  },
  methods: {
    request(){
        fetch('http://www.omdbapi.com/?apikey=31bed8d&t=avatar')
        .then(data => ((data.json())))
        .then(obj => this.filmsData = obj)
    }
  },
  mounted() {
    this.key = '31bed8d';
      
  },
};
</script>

<style scoped>
h1 {
  line-height: 100px;
}
.header {
  height: 100px;

  background-color: rgb(226, 76, 76);
}
</style>

<!--http://www.omdbapi.com/-->