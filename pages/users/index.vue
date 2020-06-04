<template>
  <section>
    <h2>{{pageTitle}}</h2>

    <ul>
      <li v-for="user of users" :key="user.id">
        <a href="#" @click.prevent="openUser(user)">{{user.title}}</a>
      </li>
    </ul>
  </section>
</template>


<script>
export default {
async asyncData() {
  const res = await fetch('https://jsonplaceholder.typicode.com/posts?_limit=10')
const users = await res.json()

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
