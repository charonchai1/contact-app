<template>
  <div class="container mt-3">
    <div class="row">
      <div class="col">
        <p class="h3 text-success fw-bold">Edit Contact</p>
        <p class="fst-italic">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Vero dolorem
          quis maxime maiores corporis eveniet debitis illo. Aliquam veniam ipsa
          commodi? Similique, illum voluptatem! Similique temporibus repellendus
          quidem aliquid provident.
        </p>
      </div>
    </div>
  </div>
  <div class="container mt-3">
    <div class="row">
      <div class="col-md-4">
        <form>
          <div class="mb-2">
            <input type="text" class="form-control" placeholder="Full Name" />
          </div>
          <div class="mb-2">
            <input type="text" class="form-control" placeholder="Photo URL" />
          </div>
          <div class="mb-2">
            <input
              class="form-control"
              type="date"
              id="birthDate"
              v-model="birthDate"
            />
          </div>
          <div class="mb-2">
            <input type="number" class="form-control" placeholder="Mobile" />
          </div>
          <div class="mb-2">
            <input type="text" class="form-control" placeholder="Address" />
          </div>
          <div class="mb-2">
            <input type="text" class="form-control" placeholder="Username" />
          </div>
          <div class="mb-2">
            <input type="text" class="form-control" placeholder="Password" />
          </div>
          <div class="mb-2">
            <input type="submit" class="btn btn-success" value="Update" />
          </div>
        </form>
      </div>
      <div class="col-md-4">
        <img
          src="https://img.icons8.com/?size=512&id=QYqNSpKRKelP&format=png"
          alt=""
          class="contact-img"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "EditContact",
};
</script>