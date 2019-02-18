<template>
  <div id="app">
    <div id="nav">
     <!-- <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>-->
    </div>
        <router-view/> 
  </div>

</template>

<script>
import Vue from 'vue'
import hiringMenu from '@/components/hiringMenu.vue'
Vue.component('v-hiringmenu', hiringMenu)
export default {
  name: 'App'
}
</script>

<style>


#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0;
  padding: 0;
}

.main{
  margin: 0;
  padding: 0;
}

.fa-icon {
    top: .125em;
    position: relative;
}

.b-main-content {
  padding-top: 1.5rem;
  padding-bottom: 1.5rem;
  margin-right: 0;
  margin-left: 0;
}

.b-form-1 {
  padding-top: 1.5rem;
  padding-bottom: 1.5rem;
  margin-right: 0;
  margin-left: 0;
  border-width: .2rem;
}
#textsize{
  font-size: 64px;
  font-weight: 600;
}
#textsize2{
  font-size: 28px;
  font-weight: 400;
}
.button {
  background-color: #4CAF50; 
  border: none;
  color: white;
  padding: 16px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 25*4px 25*2px;
  -webkit-transition-duration: 0.4s; /* Safari */
  transition-duration: 0.4s;
  cursor: pointer;
}

.button1 {
  background-color: blue; 
  color: white; 
  
}
.button1:hover {
  background-color: black;
  color: white;
}
#textsize3{
  font-size: 32px;
line-height: 40px;
  font-weight: 600;
  color: #000000
}
.device-container{
  padding-top: 30px;
}
</style>
