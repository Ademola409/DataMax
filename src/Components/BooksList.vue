<template>
    <div>
        <p v-if="isLoading">Loading...</p>
        <p v-else-if="!isLoading && error ">{{error}}</p>
        <p v-else-if="!isLoading && filteredUsers.length<1">No result found</p>
        <div v-else>
            <div class="form">
                <form>
                    <label for="search">Search</label>
                    <input type="text" id="search" v-model.trim="search">
                </form>
            </div>

            <div class="table-responsive">
                <table class="table table-bordered table-striped">
                    <thead>
                        <tr>
                            <th>Name</th>
                            <th>ISBN</th>
                            <th>Authors</th>
                            <th>Pages</th>
                            <th>Country</th>
                            <th>Released</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="user in filteredUsers" :key="user">
                            <td>{{user.name}}</td>
                            <td>{{user.isbn}}</td>
                            <td>{{user.authors[0]}}</td>
                            <td>{{user.numberOfPages}}</td>
                            <td>{{user.country}}</td>
                            <td>{{user.released}}</td>
                        </tr>
                    </tbody>
                </table>  
            </div>
            <the-footer></the-footer>
        </div>
    </div>

</template>
<script>
import axios from "axios";
import TheFooter from './TheFooter.vue';
export default {
  components:{
    TheFooter
  },

  data() {
    return {
      users: [],
      search: "",
      isLoading: false,
      error: null,
    };
  },
  
  computed: {
    filteredUsers() {
      return this.users.filter((user) => {
        return user.name.toLowerCase().match(this.search.toLowerCase());
      });
    },
  },

  methods: {
    getUser() {
      this.isLoading = true;
      this.error = null;
      const url = "https://www.anapioficeandfire.com/api/books";
      axios
        .get(url)
        .then((response) => {
          this.isLoading = false;
          this.users = response.data;
          console.log(response.data);
        })
        .catch((error) => {
          this.isLoading = false;
          this.error = "Failed to fetch data- please try again later.";
          console.log(error);
        });
    },
  },
  mounted() {
    this.getUser();
  },
};
</script>

<style scoped>
.form {
  display: flex;
  justify-content: flex-end;
}

th{
    color: rgba(0, 0, 0, 0.616);
}

</style>