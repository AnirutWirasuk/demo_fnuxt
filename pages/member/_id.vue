<template>
  <div class="container text-left">
    <div class="row">
      <div class="col-md-12 order-md-1">
        <h4 class="mb-3">Regiter member</h4>
        <form class="needs-validation" @submit.prevent="editMember" novalidate>
          <div class="row">
            <div class="col-md-6 mb-3">
              <label for="firstName">First name</label>
              <input
                type="text"
                class="form-control"
                id="firstName"
                name="firstName"
                v-model="editedMember.firstName"
                placeholder
                value
                required
              />
              <div class="invalid-feedback">Valid first name is required.</div>
            </div>
            <div class="col-md-6 mb-3">
              <label for="lastName">Last name</label>
              <input
                type="text"
                class="form-control"
                id="lastName"
                name="lastName"
                v-model="editedMember.lastName"
                placeholder
                value
                required
              />
              <div class="invalid-feedback">Valid last name is required.</div>
            </div>
          </div>

          <div class="mb-3">
            <label for="email">
              Email
              <span class="text-muted">(Optional)</span>
            </label>
            <input
              type="email"
              class="form-control"
              id="email"
              name="email"
              v-model="editedMember.email"
              placeholder="you@example.com"
            />
            <div class="invalid-feedback">Please enter a valid email address for shipping updates.</div>
          </div>
          <div class="mb-3">
            <label for="password">Password</label>
            <input
              type="password"
              class="form-control"
              id="password"
              name="password"
              v-model="editedMember.password"
              placeholder="password"
            />
          </div>

          <hr class="mb-4" />
          <button class="btn btn-primary btn-lg btn-block" type="submit">Submit</button>
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
        firstName: '',
        lastName: '',
        email: '',
        password: ''
      }
    }
  },
  created() {
    this.$axios
      .$get('https://developfirebase.firebaseio.com/member/'+this.$route.params.id+".json")
      .then(data => {
          console.log(data)
          this.editedMember = data
        // const postsArray = []
        // for (const key in data) {
        //   postsArray.push({ ...data[key], id: key })
        // }
        // this.listMember = postsArray
      })
      .catch(e => context.error(e))
  },
  methods: {
    editMember() {
      this.$axios
          .$put(
            'https://developfirebase.firebaseio.com/member/'+this.$route.params.id+".json",
            this.editedMember
          )
          .then(data => {
            // vuexContext.commit("addPost", { ...createdPost, id: data.name });
            this.$router.push("/member");
          })
          .catch(e => console.log(e));
    }
  }
  
}
</script>