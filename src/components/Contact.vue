<template>
  <div class="contact">
          <h4>Har du/ni några frågor eller vill erhålla referenser så kontakta mig!</h4>
          <div v-for="(x, index) in contact" :key="index" class="div">
            <img :src="require('@/assets/' + x.imgSrc)">
            <h4>{{x.title}}</h4>
          </div>
    </div>
</template>

<script>
export default {
    props: {
        contact: Array
    }
}
</script>

<style>

</style>