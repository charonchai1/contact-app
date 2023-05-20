<template>
  <div class="">
    <div class="row">
      <div class="col">
        <p class="h3 text-success fw-bold">View Contact</p>
      </div>
    </div>
  </div>
  <div class="container">
    <div class="row align-items-center">
      <div class="img">
        <img
          :src="contact.photoUrl"
          alt=""
          class="contact-img-big"
        />
      </div>
      <div class="">
        <ul class="list-group">
          <li class="list-group-item">
            Name :
            <span class="fw-bold">{{contact.name}}</span>
          </li>
          <li class="list-group-item">
            BirthDate :
            <span class="fw-bold">{{contact.birthdate}}</span>
          </li>
          <li class="list-group-item">
            Mobile :
            <span class="fw-bold">{{contact.mobile}}</span>
          </li>
          <li class="list-group-item">
            Address :
            <span class="fw-bold">{{contact.address}}</span>
          </li>
          <li class="list-group-item">
            Username :
            <span class="fw-bold">{{contact.username}}</span>
          </li>
          <li class="list-group-item">
            Password :
            <span class="fw-bold">{{contact.password}}</span>
          </li>
        </ul> <div class="row mt-3">
        <div class="col">
            <router-link to="/" class="btn btn-success">
            <i class="fa fa-arrow-circle-left"></i>
            Back</router-link>
        </div>
     </div>
      </div>
    </div>
    
  </div>
  
</template>

<script>
import { ContactService } from '@/services/ContactService';
export default {
  name: "ViewContact",
  data: function(){
    return{
        contactId : this.$route.params.contactId,
        loading : false,
        contact: {},
        errorMessage :null
    }
  },
  created : async function (){
    try {
        this.loading = true;
        let response = await ContactService.getContact(this.contactId);
        this.contact = response.data;
        this.loading = false;
    } catch (error) {
        this.errorMessage = error;
        this.loading = false;
    }
  }
};
</script> 


<style>

.img{
  margin: 5%;
}


</style>