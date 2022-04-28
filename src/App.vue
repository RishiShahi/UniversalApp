<script>
import Suresh from './Modules/Suresh/Suresh.vue'
import Vinod from './Modules/Vinod/Vinod.vue'
import Abdulha from './Modules/Abdulha/Abdulha.vue'
import Rajrashi from './Modules/Rajrashi/Rajrashi.vue'

const routes = {
  '/': Suresh,
  '/vinod': Vinod,
  '/abdulha': Abdulha,
  '/rajrashi': Rajrashi,
}

export default {
  data() {
    return {
      currentPath: window.location.hash
    }
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/'] || NotFound
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
		  this.currentPath = window.location.hash
		})
  }
}
</script>

<template>
  <header class="header">
    <div class="header-right">
      <a href="#/">Suresh</a> 
      <a href="#/abdulha">Abdulha</a> 
      <a href="#/vinod">Vinod</a>
      <a href="#/rajrashi">Rajrishi</a>
    </div>
  </header>

  <component :is="currentView" />
</template>

<style>
.header {
  overflow: hidden;
  background-color: #f1f1f1;
  padding: 7px 10px;
}

.header a {
  float: left;
  color: black;
  text-align: center;
  padding: 12px;
  text-decoration: none;
  font-size: 18px;
  line-height: 25px;
  border-radius: 4px;
}

.header a.logo {
  font-size: 25px;
  font-weight: bold;
}


.header a:hover {
  background-color: #ddd;
  color: black;
}

.header a.active {
  background-color: dodgerblue;
  color: white;
}


.header-right {
  display: flex;
  align-items:stretch;
  /* float: right; */
}


@media screen and (max-width: 500px) {
  .header a {
    float: none;
    display: block;
    text-align: left;
  }
  .header-right {
    float: none;
  }
}
</style>