<template>
  <div>
    <p v-if="isLoading">Loading...</p>
    <p v-else-if="!isLoading && error">{{ error }}</p>

    <div v-else>
      <div class="form">
        <form>
          <label for="search"> Search</label>
          <input type="text" id="search" v-model.trim="search" />
        </form>
      </div>

      <div class="table-responsive">
        <table class="table table-bordered table-striped ">
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
              <td>{{ user.name }}</td>
              <td>{{ user.isbn }}</td>
              <td>{{ user.authors[0] }}</td>
              <td>{{ user.numberOfPages }}</td>
              <td>{{ user.country }}</td>
              <td>{{ user.released }}</td>
            </tr>
          </tbody>
        </table>
      </div>
      <the-footer></the-footer>
    </div>
  </div>
</template>