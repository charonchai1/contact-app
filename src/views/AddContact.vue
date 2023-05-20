<template>
  <div class="container mt-3">
    <div class="row">
      <div class="col">
        <p class="h3 text-success fw-bold">Create Contact Manager</p>
      </div>
    </div>
  </div>
  <div class="container mt-4">
    <div class="row">
      <div class="col-md-100">
        <form @submit.prevent="submitCreate()"> 
          <div class="mb-2">
            <input required v-model="contact.name" type="text" class="form-control" placeholder="Full Name" />
          </div>
          <div class="mb-2">
            <input required v-model="contact.photoUrl" type="text" class="form-control" placeholder="Photo URL" />
          </div>
          <div class="mb-2">
            
            <input required v-model="contact.birthdate" class="form-control" type="date" id="birthDate" />
          </div>
          <div class="mb-2">
            <input required v-model="contact.mobile"  type="number" class="form-control" placeholder="Mobile" />
          </div>
          <div class="mb-2">
            <input required v-model="contact.address" type="text" class="form-control" placeholder="Address" />
          </div>
          <div class="mb-2">
            <input required v-model="contact.username" type="text" class="form-control" placeholder="Username" />
          </div>
          <div class="mb-2">
            <input required v-model="contact.password" type="text" class="form-control" placeholder="Password" />
          </div>
          <div class="mb-2">
            <input required type="submit" class="btn btn-success" value="Create" />
          </div>
        </form>
      </div>
        <div class="col-md-4">
            <img :src="contact.photoUrl" alt="" class="contact-img">
        </div>
    </div>
  </div>
</template>

<script>
import { ContactService } from '@/services/ContactService';

export default {
  name: "AddContact",
  data : function (){
    return {
        contact : {
            name : '',
            birthdate : '',
            mobile : '',
            address : '',
            username : '',
            password : '',
            photoUrl : '',
        }
    }
  },

  methods : {
    submitCreate : async function (){
        try {
            let response = await ContactService.createContact(this.contact);
            if(response){
                return this.$router.push('/');
            }else{
                return this.$router.push('/contacts/add')
            }
        } catch (error) {
            console.log(error);
        }
    }
  }



};
</script>