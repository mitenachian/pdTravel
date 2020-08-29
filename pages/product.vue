<template>
  <div>
    <myheader/>
    <mysearchbar/>
    <Nuxt/>
    <myfooter/>
  </div>
</template>
<script>
import myheader from '~/components/header'
import myfooter from '~/components/footer'
import mysearchbar from '~/components/searchbar'

export default {
  components: {
    myheader,
    myfooter,
    mysearchbar
  },
}
</script>
