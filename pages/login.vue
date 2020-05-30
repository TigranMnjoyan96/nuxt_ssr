<template>
  <section class="col-4 mt-3">
  <h2>Login</h2>
    <form action="">
      <div class="form-group">
        <input type="text" class="form-control">
      </div>

      <button class="btn btn-primary" type="submit">Login</button>
       <p>
        <nuxt-link to="/">To Home page</nuxt-link>
      </p>

    </form>
  </section>
</template>



<script>
export default {
  layout: 'empty'
}
</script>
