<template>
  <div class="container text-left">
    <div class="row">
      <div class="col-md-12 order-md-1">
        <h4 class="mb-3">Regiter member</h4>
        <form class="needs-validation" @submit.prevent="addMember" novalidate>
          <div class="row">
            <div class="col-md-6 mb-3">
              <label for="firstName">First name</label>
              <input type="text" class="form-control" id="firstName" name="firstName" v-model="editedMember.firstName" placeholder value required />
              <div class="invalid-feedback">Valid first name is required.</div>
            </div>
            <div class="col-md-6 mb-3">
              <label for="lastName">Last name</label>
              <input type="text" class="form-control" id="lastName" name="lastName" v-model="editedMember.lastName" placeholder value required />
              <div class="invalid-feedback">Valid last name is required.</div>
            </div>
          </div>

          <div class="mb-3">
            <label for="email">
              Email
              <span class="text-muted">(Optional)</span>
            </label>
            <input type="email" class="form-control" id="email" name="email" v-model="editedMember.email" placeholder="you@example.com" />
            <div class="invalid-feedback">Please enter a valid email address for shipping updates.</div>
          </div>
          <div class="mb-3">
            <label for="password">Password</label>
            <input type="password" class="form-control" id="password" name="password" v-model="editedMember.password" placeholder="password" />
          </div>

          <hr class="mb-4" />
          <button class="btn btn-primary btn-lg btn-block" type="submit">Submit</button>
          <button class="btn btn-primary btn-lg btn-block" type="button" @click="btnCancel()">Cancel</button>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      editedMember: {
        firstName: "",
        lastName: "",
        email: "",
        password: ""
      }
    }
  },
  methods: {
    addMember() {
      this.$axios
          .$post(
            "https://developfirebase.firebaseio.com/member.json",
            this.editedMember
          )
          .then(data => {
            console.log(data);
            this.$swal.fire({
              position: 'top-end',
              type: 'success',
              title: 'Your work has been saved',
              showConfirmButton: false,
              timer: 1500
            })
            // vuexContext.commit("addPost", { ...createdPost, id: data.name });
            this.$router.push("/authen");
          })
          .catch(e => console.log(e));
    },
    btnCancel(){
      this.$swal.fire({
        position: 'top-end',
        type: 'success',
        title: 'Your work has been saved',
        showConfirmButton: false,
        timer: 1500
      })
    }
  }
}
</script>