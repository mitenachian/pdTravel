<template>
<div id="headerArea" >
  <div>
    <b-nav align="right">
      <b-nav-item href="#"><b-icon icon="clipboard-check"></b-icon>訂單查詢</b-nav-item>
      <b-nav-item href="#"><b-icon icon="person-fill"></b-icon>會員登入</b-nav-item>
    </b-nav>
  </div>
  <!-- As a link -->
  <b-navbar toggleable="sm"  type="dark" variant="primary">
    <b-navbar-brand>
      <nuxt-link to="/"><img src="@/assets/toplogo.svg" height="50px" alt=" 彭大家族旅遊社團"></nuxt-link>
    </b-navbar-brand>
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-item-dropdown  text="國外旅遊" right>
          <b-dropdown-item to="/product/">東北亞demo</b-dropdown-item>
          <b-dropdown-item href="#">東南亞</b-dropdown-item>
          <b-dropdown-item href="#">歐洲</b-dropdown-item>
          <b-dropdown-item href="#">大洋洲</b-dropdown-item>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown text="國內旅遊" right>
          <b-dropdown-item href="#" disabled>---本島---</b-dropdown-item>
          <b-dropdown-item href="#">北部</b-dropdown-item>
          <b-dropdown-item href="#">中島</b-dropdown-item>
          <b-dropdown-item href="#">南島</b-dropdown-item>
          <b-dropdown-item href="#">東部</b-dropdown-item>
          <div class="dropdown-divider"></div>
          <b-dropdown-item href="#" disabled>---離島---</b-dropdown-item>
          <b-dropdown-item href="#">金門</b-dropdown-item>
          <b-dropdown-item href="#">澎湖</b-dropdown-item>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown text="訂房" right>
          <b-dropdown-item href="#">國內訂房</b-dropdown-item>
          <b-dropdown-item href="#">國外訂房</b-dropdown-item>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown  text="票券/交通" right>
          <b-dropdown-item href="#">包車</b-dropdown-item>
          <b-dropdown-item href="#">租車</b-dropdown-item>
          <b-dropdown-item href="#">接送機</b-dropdown-item>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown  text="票券/交通" right>
          <b-dropdown-item href="#">包車</b-dropdown-item>
          <b-dropdown-item href="#">租車</b-dropdown-item>
          <b-dropdown-item href="#">接送機</b-dropdown-item>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown  text="機票" right>
          <b-dropdown-item href="#">個人機票</b-dropdown-item>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown  text="旅平險" right>
          <b-dropdown-item href="#">星光產險</b-dropdown-item>
          <b-dropdown-item href="#">國泰產險</b-dropdown-item>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown  text="推薦行程" right>
          <b-dropdown-item href="#">滑雪</b-dropdown-item>
          <b-dropdown-item href="#">賞鯨</b-dropdown-item>
          <b-dropdown-item href="#">包車/一日遊</b-dropdown-item>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown class="white" text="彭大家族集團" right>
          <b-dropdown-item href="#">彭大家族旅行社</b-dropdown-item>
          <b-dropdown-item href="#">彭大家族購物商成</b-dropdown-item>
          <b-dropdown-item href="#">彭大家族株式會社</b-dropdown-item>
          <b-dropdown-item href="#">彭大旅遊保險</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>
</template>
<script>

export default {

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
.nav-item a:hover{
  text-decoration: underline;
}

a {
  text-decoration: none;
  background-color: transparent;
}
.nav{
  font-size: 14px;
  background-color: #e2f2ff;
}
@media screen and (max-width: 480px) {
  .navbar{
    background-image: none;
  }
}
@media screen and (min-width:1024px){
  .navbar{
    background-image: url('../assets/travel_together.svg');
    background-repeat: no-repeat;
    background-position: 20% 0%;
    background-color: rgb(0, 160, 232) !important;
  }
}
</style>