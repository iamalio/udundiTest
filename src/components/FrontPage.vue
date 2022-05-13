<template>
<section id="frontpage" class="container-fluid frontpage">
  <div class="row">
    <div class="frontpage__leftBar col-sm-3 col-md-3 col-lg-3">
      <div class="frontpage__leftBarContent">
        <h1 class="">Explore</h1>
        <div class="frontpage__ctaWrapper">
          <img src="../assets/Plus.svg" class="frontpage__ctaWrapperButton"/>
          <p>More Details</p>
        </div>
      </div>
    </div>
  </div>
<PopUp />
</section>
</template>

<script>
import PopUp from './PopUp.vue'

export default {
  name: 'FrontPage',
   components: {
      PopUp
   }
}
</script>

<style >
@import '@/assets/_frontpage.scss';
</style>
