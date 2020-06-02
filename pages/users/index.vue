<template>
  <section>
    <h2>{{pageTitle}}</h2>

    <ul>
      <li v-for="user of users" :key="user.id">
        <a href="#" @click.prevent="openUser(user)">{{user.name}}</a>
      </li>
    </ul>
  </section>
</template>


<script>
export default {
async asyncData({$axios}) {
  const users = await $axios.$get('https://jsonplaceholder.typicode.com/users')
  console.log(users);

  return {users}
},
  data() {
    return {
        pageTitle: 'Users page'
    }
  },
  methods: {
    openUser(user) {

      this.$router.push('/users/' + user.id)
    }
  }
}
</script>
