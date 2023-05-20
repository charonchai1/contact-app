<template>
  <aside class="sidebar">
    <ul class="nav flex-column">
      <li class="nav-item">
        <a class="font-style" href="/">Home</a>
      </li>
    
      <li class="nav-item">
        <a class="font-style" href="/contacts/add">Create User</a>
        
      </li>
      <!-- <router-link to="/contacts/add" class="btn btn-success btn-sm"
        ><i>Craete User</i></router-link
      > -->
    </ul>
  </aside>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style>
.sidebar {
    color: violet;
  width: 250px;
  background-color: #f8f9fa;
  padding: 20px;
  position: fixed;
  height: 100%;
}

.sidebar-header {
  margin-bottom: 20px;
}

.nav-item {
  margin-bottom: 10px;
}
.nav-item:hover {
  background-color: #d1e7dd;
}
.font-style{
    color: black;
    text-decoration: none;
    font-weight: 600;
}

</style>
