<template>
  <div id="app">

    <!-- BARRA DE NAVEGACION-->
<div>
  <b-navbar toggleable="lg" type="dark" class="bg-success">
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-navbar-brand href="#" class="px-3"> <router-link to="/" class="text-white eliminarDecoracion fs-7">Home</router-link> </b-navbar-brand>
        <b-navbar-brand href="#" class="px-1"> <router-link to="/administracion" class="text-white eliminarDecoracion fs-7">Administracion</router-link> </b-navbar-brand>
        <b-navbar-brand href="#" class="px-2"> <router-link to="/about" class="text-white eliminarDecoracion fs-7">About</router-link> </b-navbar-brand>
        <b-nav-item href="#" class="px-2 fs-7">Link</b-nav-item>
        <b-nav-item href="#" class="px-2 fs-7" disabled>Disabled</b-nav-item>
      </b-navbar-nav>

    </b-collapse>
  </b-navbar>
</div>
<!-- FIN BARRA DE NAVEGACION-->



    <router-view/>
  </div>
</template>

<script>
import { mapActions } from 'vuex';
export default{
  name: 'app',
  data:function(){
    return{

    }
  },
  props:{},
  components:{},
  methods:{
    ...mapActions('datos_cursos',['consultarCursos', 'consultarDatosTabla']),
  },
  computed:{},
  watch:{},
  beforeMount(){
    this.consultarCursos();
    this.consultarDatosTabla();
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.eliminarDecoracion{
  text-decoration: none;
}
</style>
