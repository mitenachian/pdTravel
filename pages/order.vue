<template>
  <div>
    <myheader/>
    <Nuxt/>
    <myfooter/>
  </div>
</template>
<script>
import myheader from '~/components/header'
import myfooter from '~/components/footer'

export default {
  components: {
    myheader,
    myfooter
  },
}
</script>

<style scoped>
#order_content{
    font-family: 'Noto Sans TC', sans-serif;
}
</style>