<template>

  <div  class="position">
    <Navbar />
    <Sidebar />
  </div>
  
  <div class="container">
    <div class="content">
      <router-view />
    </div>
  </div>
</template>



<script>
import Navbar from "./components/Navbar.vue";
import Sidebar from "./components/Sidebar.vue";

export default {
  components: { Navbar, Sidebar },
  name: "app",
};
</script>



<style>

.content {
  position: absolute;
  left: 300px;
  width: 100%;
  height: 300px; /*This could be anything, content should scroll vertical*/
}
.container {
  /* width: 100% !important;  */
  height: 100% !important;
  display: flex;
  margin: 0 !important;
  padding: 0 !important;
  flex-direction: row;
}
.position{
     background-color:#990000;
  position:fixed;  
  z-index:1; /*Add this*/
  width:100%;
  height:50px;
  text-align:center;
  vertical-align:middle;
  line-height:50px;
  top:0px;
 }
</style>
