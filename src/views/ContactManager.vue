<template>
  <div class="">
    <div class="row">
      <div class="col">
        <form>
          <div class="row">
            <div class="col-md-6">
              <div class="my-3">
                <h1>Contact Manager</h1>
              </div>
              <div class="col-md-6">
                <input
                  v-model="searchValue"
                  type="text"
                  class="form-control"
                  placeholder="Search Name"
                />

                <div v-if="searchValue && !userList.length">No user Found</div>
              </div>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
  <!-- Spinnner -->
  <div v-if="loading">
    <div class="container">
      <div class="row">
        <div class="col">
          <Spinner />
        </div>
      </div>
    </div>
  </div>

  <div v-if="!loading && errorMessage">
    <div class="container">
      <div class="row">
        <div class="col">
          <p class="h3 text-danger fw-bold">{{ errorMessage }}</p>
        </div>
      </div>
    </div>
  </div>
  <div class="container mt-3" v-if="userList.length">
    <div class="list-card">
      <div class="" v-for="user of userList" :key="user">
        <div class="card layout list-group-item-success shadow-lg">
          <div class="card-body layout">
            <img :src="user.photoUrl" alt="" class="contact-img" />
            <ul class="list-group">
              <li class="list-group-item">
                Name :
                <span class="fw-bold">{{ user.name }}</span>
              </li>
              <li class="list-group-item">
                BirthDate :
                <span class="fw-bold">{{ user.birthdate }}</span>
              </li>
              <li class="list-group-item">
                Mobile :
                <span class="fw-bold">{{ user.mobile }}</span>
              </li>
            </ul>
            <div
              class="d-flex flex-column justify-content-center align-items-center"
            >
              <router-link
                :to="`/contacts/view/${user.id}`"
                class="btn btn-warning my-1"
              >
                <i class="fa fa-eye"></i>
              </router-link>
              <router-link
                :to="`/contacts/edit/${user.id}`"
                class="btn btn-primary my-1"
              >
                <i class="fa fa-pen"></i>
              </router-link>
              <button
                class="btn btn-danger my-1"
                @click="clickDeleteContact(user.id)"
              >
                <i class="fa fa-trash"></i>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ContactService } from "@/services/ContactService";
import Spinner from "@/components/Spinner.vue";

export default {
  name: "ContactManager",
  components: { Spinner },
  data: function () {
    return {
      searchValue: "",
      loading: false,
      contacts: [],
      errorMessage: null,
    };
  },
  computed: {
    userList() {
      if (this.searchValue.trim().length > 0) {
        return this.contacts.filter((user) =>
          user.name
            .toLowerCase()
            .includes(this.searchValue.trim().toLowerCase())
        );
      }
      return this.contacts;
    },
  },
  created: async function () {
    try {
      this.loading = true;
      let response = await ContactService.getAllContacts();
      this.contacts = response.data;
      this.loading = false;
    } catch (error) {
      this.errorMessage = error;
      this.loading = false;
    }
  },
  methods: {
    clickDeleteContact: async function (contactId) {
      try {
        this.loading = true;
        let response = await ContactService.deleteContact(contactId);
        if (response) {
          let response = await ContactService.getAllContacts(); // fresh data
          this.contacts = response.data;
          this.loading = false;
        }
      } catch (error) {
        this.errorMessage = error;
        this.loading = false;
      }
    },
  },
};
</script>

<style>
.layout {
  display: flex;
  flex-direction: row;
  width: 500px;
  gap: 8px;
  justify-content: center;
  align-items: center;
  margin: 8px 0px;
}
.list-card {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px
  
}
</style>