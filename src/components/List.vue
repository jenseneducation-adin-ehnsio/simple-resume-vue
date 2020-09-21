<template>
  <div class="list">
      <h4>{{title}}</h4>
      <ul v-for="x in list" :key="x.title">
        <li>
            <p  v-show="!x.place == ''">{{x.duration}} | {{x.place}}</p>
            <p :class="fatOrNot(x.place)" >{{x.title}}</p>
        </li>
      </ul>
  </div>
</template>

<script>
export default {
    props: {
        title: String,
        list: Array
    },
    methods: {
      fatOrNot(x) {
        if(x == '') {
          return ''
        }
        else {
          return 'mono'
        }
      }
    }

  
}
</script>

<style lang="scss" >
  li > p {
    
    font-weight: 500;
    margin: 0;
    font-size: 1.2em;
  }
  li {
    margin: 10px 0 10px 0;
  }
  .mono {
    letter-spacing: normal;
    font-weight: 400;
    font-size: 17px;
    padding: 0 !important;
    line-height: 120%;
  }
</style>