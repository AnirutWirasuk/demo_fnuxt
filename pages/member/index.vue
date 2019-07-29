<template>
  <div class="container">
    <table class="table">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">First</th>
          <th scope="col">Last</th>
          <th scope="col">Email</th>
          <th scope="col">Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="Member in listMember" :key="Member.id">
          <th scope="row">1</th>
          <td>{{ Member.firstName }}</td>
          <td>{{ Member.lastName }}</td>
          <td>{{ Member.email }}</td>
          <td>
            <button type="button" class="btn btn-primary" @click="pageEdit(Member.id)">Edit</button>
            <button type="button" class="btn btn-danger">Del</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  data() {
    return {
      listMember: []
    }
  },
  created() {
    this.$axios
      .$get('https://developfirebase.firebaseio.com/member.json')
      .then(data => {
        const postsArray = []
        for (const key in data) {
          postsArray.push({ ...data[key], id: key })
        }
        this.listMember = postsArray
      })
      .catch(e => context.error(e))
  },
  methods: {
    pageEdit(id) {
      this.$router.push("/member/" +id);
    }
  }
}
</script>