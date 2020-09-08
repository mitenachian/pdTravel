<template>
<section id="headerArea" >
    <b-nav align="right">
      <b-nav-item href="#"><b-icon icon="clipboard-check"></b-icon>訂單查詢</b-nav-item>
      <b-nav-item href="#"><b-icon icon="person-fill"></b-icon>會員登入</b-nav-item>
    </b-nav>
  <!-- As a link -->
  <b-navbar toggleable="md"  type="dark" variant="primary">
    <b-navbar-brand>
      <nuxt-link to="/"><img src="~/assets/toplogo.svg" height="50px" alt=" 彭大家族旅遊社團"></nuxt-link>
    </b-navbar-brand>
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-item-dropdown v-for="items in menu" :key="items.link_id"  :text="items.link_title" right>
          <b-dropdown-item v-for="sub_items in items.children" :key="sub_items.link_id" :to="sub_items.route_path">
            {{sub_items.link_title}}
          </b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</section>
</template>
<script>
import menu_data from '~/assets/demo_navData.json'
export default {
 data() {
      return {
        menu:[],
      }
 },
  async fetch() {
      this.menu = menu_data;
      // this.posts = await this.$http.$get(
      //   'https://jsonplaceholder.typicode.com/posts'
      // )
  }
}
</script>
<style scoped>
#headerArea{
  font-family: 'Noto Sans TC', sans-serif;
  position:sticky; 
  left:0;           /* top left corner should start at leftmost spot */
  top:0;            /* top left corner should start at topmost spot */
  width:100%;      /* take up the full browser width */
  z-index:200;  /* high z index so other content scrolls underneath */
  height:113px;     /* define height for content */
}
.nav{
  font-size: 14px;
  background-color: #e2f2ff;
}
.navbar{
    /*background-image: url('/travel_together.svg');*/
    background-image: url('../assets/travel_together.svg');
    background-repeat: no-repeat;
    background-position: 20% 0%;
    background-color: rgb(0, 160, 232) !important;
  }
@media screen and (max-width: 1280px) {
  .navbar{
    background-image: none;
  }
}

</style>