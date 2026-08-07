<template>
  <h2 @click="show_video">123123</h2>
</template>

<script>
export default {
  data() {
    return {

    }
  },
  methods: {
    show_video(){
      this.$router.push('/about')
    }
  }
}

</script>

<style>
.map {
  width: 100%;
  height: 800px;
}
</style>