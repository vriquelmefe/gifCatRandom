<template>
  <div class="hello text-center">
    <h1 class="titulo font-weight-bold">{{ msg }}</h1>
    <div class="bg-danger ">
      <form class="pt-3 ">
            <label for="">Titulo: </label>
            <input type="text" v-model="titulo" placeholder="cuchito">
            <div class="p-2">
            <label for="" >Filtro: </label>
            <select id="" class="pr-4 pl-1 py-1" v-model="filtro">
              <option value="blur">Blur</option>
              <option value="mono">Mono</option>
              <option value="sepia">Sepia</option>
              <option value="negative">Negative</option>
              <option value="paint">Paint</option>
            </select>
            </div>
            <div class="p-2">
            <label for="">Color:  </label>
            <select id="" class="py-1" v-model="color">
              <option value="red">Rojo</option>
              <option value="green">Verde</option>
              <option value="yellow">Amarillo</option>
              <option value="blue">Azul</option>
              <option value="white">Blanco</option>
              <option value="black">Negro</option>
            </select>
            <div class="circleColor mx-3 py-2" :style="{backgroundColor : this.color}"></div>
            </div>
            <div>
            <label>Tamaño: </label>
            <input type="number" v-model="tamanio" placeholder="300,400,500,etc">
            </div>
        
      </form>
     </div>
    <div class="divButton pt-3">
      <button class="btn btn-outline-secondary bg-light text-dark" @click="obtenerCat">Obtener mi gatito</button>   
    </div>
    <div class="mt-5">
      <img :src="gatito" alt="">
    </div>
  </div>
</template>

<script>
export default {
  name: "GitCat",
  props: {
    msg: String,
  },
  data: () => ({
    titulo : "",
    filtro : "",
    color : "",
    tamanio : "",
    gatito: ""
  }),
  methods:{
    obtenerCat(){
      fetch(`https://cataas.com/cat/gif/says/${this.titulo}?filter=${this.filtro}&color=${this.color}&size=${this.tamanio}`)
        .then(resp => this.gatito = resp.url)
    }  
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
form{
  padding-left: 45vw;
  text-align: left;
}

label{ 
  font-weight: bold;

}
.circleColor{
  border-radius: 50%;
  height: 30px;
  width: 30px;
  display: inline-block;
  vertical-align: middle;
}
.titulo{
  height:  100px;
  padding-top: 40px;
  margin: 0 auto;
}
</style>
