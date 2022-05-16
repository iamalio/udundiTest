<style >
@import '@/assets/_popup.scss';
@import '@/assets/_animations.scss';
</style>

<template>
<section id="popup" class="popup__main col-sm-3 col-md-7 col-lg-5">
    <div id="fadeIn" class="popup__contentHidden">
<img src="../assets/Close.svg" class="popup__ctaClose" @click="animateBubbleOut()"/>
<h2 class="popup__ctaHeading">Explore</h2>
    <img src="../assets/Path.svg" class="popup__ctaHeadingUnder"/>

<p class="popup__ctaText col-sm-4 col-md-11 col-lg-11">Sed ut perspiciatis unde omnis iste natus error sit voluptatem
accusantium doloremque laudantium, totam rem aperiam, eaque
ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae
dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas
sit aspernatur aut odit aut fugit, sed quia consequuntur magni
dolores eos qui ratione voluptatem sequi nesciunt. Neque porro
quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur,
adipisci velit, sed quia non numquam eius modi tempora incidunt ut
labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad
minima veniam, quis nostrum exercitationem ullam corporis suscipit
laboriosam, nisi ut aliquid ex ea commodi consequatur?</p>
<button class="popup__ctaButton">Read More</button>

    </div>
    

</section>
</template>

<script>

export default {
  name: 'PopUp',
  mounted() {
  this.fadeIn();
},
methods: {
    
  animateBubbleOut: function() {
      let disappear = 900;
      let hideDelay = 300;
      let resetclasses = 1000;
      let popup = document.getElementById("popupComponent");
          popup.classList.remove("animate__bubbleExpand");
          popup.classList.add("animate__bubblePop");
          setTimeout(function() {
         popup.classList.add("popup");
          
       }, disappear)
       
        setTimeout(function() {
        let pagecontent = document.getElementById("page-content");
       
          pagecontent.classList.remove("animate__flash");
          pagecontent.classList.add("animate__flashReverse", "frontpage__leftBarContent");
      }, hideDelay)    



        setTimeout(function() {
        let pagecontent = document.getElementById("page-content");
       
          pagecontent.classList.remove("animate__flashReverse", "frontpage__leftBarContent");
          pagecontent.classList.add("frontpage__leftBarContent");
          let popup = document.getElementById("popupComponent");
          popup.classList.remove("animate__bubblePop");
          popup.classList.add("popup");
      }, resetclasses) 
      



    },
  
        fadeIn: function() {
        let fadeInTimer = 1500;
              let fadeIn = document.getElementById("fadeIn");

        setTimeout(function() {
        fadeIn.classList.remove("popup__contentHidden");
        fadeIn.classList.add("animate__fadeInLeft");
       }, fadeInTimer)
    }
}
  

}

</script>

