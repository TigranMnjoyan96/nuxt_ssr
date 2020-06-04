<template>
  <section>
    <h2>User {{$route.params.id}}</h2>
     <b>{{user.title}}</b>
  </section>
</template>


<script>
export default {
  // validate({params}) {
  //   return /^\d+$/.test(params.id)
  // },
  async asyncData() {
console.log(this.$route.params.id, 'dj');

  const res = await fetch('https://jsonplaceholder.typicode.com/users/' + $route.params.id)
const users = await res.json()

  return {user}
},
}
</script>
