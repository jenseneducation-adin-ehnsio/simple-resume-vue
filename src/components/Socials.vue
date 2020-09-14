<template>
  <div class="socials">
    <div v-for="x in socials" :key="x.title">
        <a target="_blank" :href="x.url">
            <img :src="require('@/assets/' + x.imgSrc)" :alt="x.title">
            <p>{{x.title}}</p>
        </a>
    </div>
 </div>
</template>

<script>
export default {
    props: {
        socials: Array
    }

}
</script>

<style>

</style>