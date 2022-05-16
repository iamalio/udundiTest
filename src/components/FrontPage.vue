<style >
@import '@/assets/_animations.scss';
@import '@/assets/_frontpage.scss';


</style>

<template>
<section id="frontpage" class="container-fluid frontpage">
  <div class="row">
    <div class="frontpage__leftBar col-sm-3 col-md-3 col-lg-3">
      <div  id="page-content" class="frontpage__leftBarContent">
        <h1 id="mainheading" class="frontpage__leftBarContentHeading" >Explore</h1>
        <div class="frontpage__ctaWrapper">

          <button id="openpopup" class="frontpage__ctaWrapperButton frontpage__ctaWrapperButtonBorder" @click="animateBubbleIn()">
          </button>
          <p >More Details</p>
        
        </div>
          <section class="popup__social ">
          <img src="../assets/Facebook.svg" class="popup__socialIcon"/>
          <img src="../assets/Instagram.svg" class="popup__socialIcon"/>


        </section>
                                    

      </div>
      <PopUp id="popupComponent" class="popup" />

      
    </div>
  </div>
</section>
</template>

<script>
import PopUp from './PopUp.vue'

export default {
  name: 'FrontPage',
    components: {
      PopUp
    },
    mounted: function() {
      document.onreadystatechange = () => {
        if (document.readyState == "complete") {
          this.exploreIntro();
        }
      }
     
    },
    methods: {
      exploreIntro: function() {
        let mainheading = document.getElementById("mainheading");
        let introdone = 3000;
        mainheading.classList.add("animate__bounceIn");
        setTimeout(function() {
           mainheading.classList.remove("animate__bounceIn");
        }, introdone)
      },


      animateBubbleIn: function() {
        let bubbleDelay = 100;
        let hideDelay = 800;
        let clickeffect = 100;
        let openpopup = document.getElementById("openpopup");

        openpopup.classList.remove("frontpage__ctaWrapperButtonBorder");
        openpopup.classList.add("activate");

        setTimeout(function() {
          openpopup.classList.remove("activate");
          openpopup.classList.add("frontpage__ctaWrapperButtonBorder");
        }, clickeffect)

      
      setTimeout(function() {
        let popup = document.getElementById("popupComponent");
          popup.classList.remove("popup");
          popup.classList.add("animate__bubbleExpand");
      }, bubbleDelay)

      setTimeout(function() {
        let pagecontent = document.getElementById("page-content");      
          pagecontent.classList.remove("frontpage__leftBarContent");
          pagecontent.classList.add("animate__flash");
      }, hideDelay)     
    },


    
  }

}
</script>

