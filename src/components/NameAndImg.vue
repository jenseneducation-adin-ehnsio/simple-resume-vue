<template>
  <div class="name-and-img">
      <h1 class="title-top">{{name.first}} <span class="green">{{name.last}}</span></h1>
      <img class="avatar" alt="Vue logo" src="@/assets/avatar.jpg">
  </div>
</template>

<script>
export default {
    props: {
        name: Object,
    }
}
</script>

<style>

</style>