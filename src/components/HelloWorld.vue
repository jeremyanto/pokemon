<template>
  <div style="background-color:white; margin-right: 400px; margin-left: 400px; border-radius:15px;" >
<label for="site-search"> Recherche ton pokemon : </label>
<input type="search" id="site-search" name="q"
    aria-label="Search through site content">
<button v-on:click="Search">Go !</button>

<p>Nom : {{this.namepk}}</p>
  <img id ='imge'>
  <p>Poids : {{this.heightpk}}</p>
  <p>Pokemon de types : </p>
  <ul id="v-for-object" class="demo">
    <li v-for="value in this.typespk">
      {{ value.type.name }}
    </li>
  </ul>

 </div>
</template>
<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',

      info: null,
      namepk: null,
      heightpk: null,
      imgurl: null,
      typespk: null
    }
  },

  methods: {
    clicked: function () {
      console.log('click')
    },
    hide: function () {
      console.log('hide')
      document.getElementById('idh1').style.display = 'none'
    },
    show: function () {
      console.log('show')
      document.getElementById('idh1').style.display = 'block'
    },
    create: function () {
      var txt = 'test'
      var h = document.createElement('p')
      var t = document.createTextNode(txt)
      h.appendChild(t)
      var currentDiv = document.getElementById('create')
      currentDiv.appendChild(h)

    },
    Search: function () {
      console.log("search")
      var url = document.getElementById("site-search").value
      console.log(url)
      axios
   .get('https://pokeapi.co/api/v2/pokemon/' + url)

   .then(response =>
    {
    this.info = response.data
        this.namepk = this.info.name
        this.heightpk = this.info.height
        this.imgurl = this.info.sprites.back_default
        this.typespk = this.info.types
        var imgdom = document.getElementById('imge')
        imgdom.src = this.info.sprites.back_default


    })

    }
  },

}
</script>