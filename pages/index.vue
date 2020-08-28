<template>
  <div>
    <myheader/>
    <mybanner/>
    <mysearchbar/>
    <Nuxt/>
    <myfooter/>
  </div>
</template>
<script>
import myheader from '~/components/header'
import myfooter from '~/components/footer'
import mybanner from '~/components/banner'
import mysearchbar from '~/components/searchbar'

export default {
  components: {
    myheader,
    myfooter,
    mybanner,
    mysearchbar
  },

}
</script>

<style>
.links {
  padding-top: 15px;
}

</style>
