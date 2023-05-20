<template>
  <aside class="sidebar">
    <ul class="nav flex-column">
      <li class="nav-item">
        <a class="nav-link" href="/">Home</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="/contacts/add">Create User</a>
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

</style>