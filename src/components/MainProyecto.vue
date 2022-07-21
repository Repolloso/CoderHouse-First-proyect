<template lang="html">

    <div>
        <h1>Esto es la main page</h1>
        <!-- send the flag to the father (app) -->
        <button class="btn btn-primary" @click="changeValue">Loguot</button>
    </div>

</template>

<script lang="js">

  export default  {
    name: 'main-proyecto',
    props: [],
    mounted () {

    },
    data () {
      return {

      }
    },
    methods: {
      changeValue () {
          this.$emit('changeFlagFromMain');
      }
    },
    computed: {

    }
}

</script>

<style scoped>

</style>
