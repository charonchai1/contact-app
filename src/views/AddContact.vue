<template>
  <div class="container mt-3">
    <div class="row">
      <div class="col">
        <p class="h3 text-success fw-bold">Add Contact</p>
        <p class="fst-italic">djwqdklqklwqjklwqjklwqjkl</p>
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
             <label for="birthDate">Date of Birth:</label>
    <input type="date" id="birthDate" v-model="birthDate">
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
            <input type="submit" class="btn btn-success" value="Create">
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AddContact",
};
</script>