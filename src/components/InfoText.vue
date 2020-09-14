<template>
  <div class="info-text">
      <h4>{{info.title}}</h4>
      <p>{{info.info}}</p>
  </div>
</template>

<script>
export default {
    props: {
        info: Object
    }
}
</script>

<style>

</style>