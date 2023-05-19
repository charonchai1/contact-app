<template>
  <div class="container mt-3">
    <div class="row">
      <div class="col">
        <p class="h3 text-success fw-bold">View Contact</p>
        <p class="fst-italic">
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quo
          architecto quam tenetur dolorem reiciendis quia aspernatur amet
          nostrum possimus velit! Amet harum animi incidunt dolore dignissimos
          facilis dolorum laudantium exercitationem.
        </p>
      </div>
    </div>
  </div>
  <div class="container">
    <div class="row align-items-center">
      <div class="col-md-4">
        <img
          src="https://img.icons8.com/?size=512&id=QYqNSpKRKelP&format=png"
          alt=""
          class="contact-img-big"
        />
      </div>
      <div class="col-md-6">
        <ul class="list-group">
          <li class="list-group-item">
            Name :
            <span class="fw-bold">Name</span>
          </li>
          <li class="list-group-item">
            BirthDate :
            <span class="fw-bold">BirthDate</span>
          </li>
          <li class="list-group-item">
            Mobile :
            <span class="fw-bold">Mobile</span>
          </li>
          <li class="list-group-item">
            Address :
            <span class="fw-bold">Address</span>
          </li>
          <li class="list-group-item">
            Username :
            <span class="fw-bold">Username</span>
          </li>
          <li class="list-group-item">
            Password :
            <span class="fw-bold">Password</span>
          </li>
        </ul>
      </div>
    </div>
     <div class="row mt-3">
        <div class="col">
            <router-link to="/" class="btn btn-success">
            <i class="fa fa-arrow-circle-left"></i>
            Back</router-link>
        </div>
     </div>
  </div>
</template>

<script>
export default {
  name: "ViewContact",
};
</script> 