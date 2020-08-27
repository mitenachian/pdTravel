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
html .body{
  font-family: 'Noto Sans TC', sans-serif;
}
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.links {
  padding-top: 15px;
}

</style>
