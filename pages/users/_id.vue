<template>
  <section>
    <h2>User {{$route.params.id}}</h2>
     <b>{{user.email}}</b>
  </section>
</template>


<script>
export default {
  validate({params}) {
    return /^\d+$/.test(params.id)
  },
  async asyncData({$axios, params}) {

  const user = await $axios.$get('https://jsonplaceholder.typicode.com/users/' + params.id)


  return {user}
},
}
</script>
