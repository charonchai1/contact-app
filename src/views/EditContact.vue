<template>
  <div class="">
    <div class="row">
      <div class="col">
        <p class="h3 text-success fw-bold">Edit Contact</p>
       
      </div>
    </div>
  </div>
  <div class="">
    <div class="row">
      <div class="col-md-4">
        <form @submit.prevent ="updateSubmit()">
          <div class="mb-2">
            <input required v-model="contact.name" type="text" class="form-control" placeholder="Full Name" />
          </div>
          <div class="mb-2">
            <input required v-model="contact.photoUrl" type="text" class="form-control" placeholder="Photo URL" />
          </div>
          <div class="mb-2">
            <input
              required class="form-control"
              type="date"
              id="birthDate"
              v-model="contact.birthdate"
            />
          </div>
          <div class="mb-2">
            <input required v-model="contact.mobile" type="number" class="form-control" placeholder="Mobile" />
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
            <input required type="submit" class="btn btn-success" value="Update" />
          </div>
        </form>
      </div>
      <div class="col-md-4">
        <img
          :src="`${contact.photoUrl}`"
          alt=""
          class="contact-img"
        />
      </div>
    </div>
  </div>
</template>

<script>
import { ContactService } from '@/services/ContactService';
export default {
  name: "EditContact",
  data : function (){
    return{ 
    contactId : this.$route.params.contactId,
    loading: false,
    contact : {},
    errorMessage : null

    }
},
created : async function (){
    try {
        this.loading = true;
        let response = await ContactService.getContact(this.contactId);
        this.contact = response.data
        this.loading = false;
    } catch (error) {
        this.errorMessage = error;
        this.loading = false;
    }
},
methods : {
    updateSubmit : async function (){
          try {
            let response = await ContactService.updateContact(this.contact, this.contactId);
            if(response){
                return this.$router.push('/');
            }else{
                return this.$router.push(`/contacts/edit/${this.contactId}`)
            }
        } catch (error) {
            console.log(error);
        }
    }
    
}
};
</script>