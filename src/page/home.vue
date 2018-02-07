<template>
   <div class="layout-box">
       <div class="home-contain">
           <div class="banner big" id="banner">
            <div>
              <a href="javascript:;" target="_blank"><img src="../assets/images/01.jpg"></a>
            </div>
            <div>
              <a href="javascript:;" target="_blank"><img src="../assets/images/02.jpg"></a>
            </div>
            <div>
              <a href="javascript:;" target="_blank"><img src="../assets/images/01.jpg"></a>
            </div>
            <div>
              <a href="javascript:;" target="_blank"><img src="../assets/images/02.jpg"></a>
            </div>
        </div>
       </div>
   </div>
</template>
    <script src="../assets/lib/jquery/jquery.min.js"></script>
    <script src="../assets/lib/slick/slick.min.js"></script>
<script>
     // 轮播图
    $(function () {
        var $banner = $("#banner");
        if($banner.children().length == 0)
        	return;
        $banner.slick({
          dots: true,
          infinite: true,
          centerMode: true,
          variableWidth: true,
          autoplay: true,
          autoplaySpeed: 5000,
          slidesToShow: 3,
          slidesToScroll: 3,
          arrows: false
        });
        
        var $envBanner = $('#env_banner')
        if ($envBanner.children().length == 0)
          return
        $envBanner.slick({
          dots: false,
          infinite: true,
          centerMode: true,
          variableWidth: true,
          autoplay: true,
          autoplaySpeed: 5000,
          slidesToShow: 3,
          slidesToScroll: 3,
          arrows: true
        })
        $envBannerTitle = $('#env_banner_title');
        setEnvCurrentText();
        $envBanner.on('afterChange',function(event, slick, currentSlide){
          setEnvCurrentText();
        })
        function setEnvCurrentText () {
          var $currentText = $envBanner.find('.slick-current .text');
          $envBannerTitle.html($currentText.html());
        }
    })
</script>
<script>
    export default {
        
    }
</script>
<style scoped>
@import '../assets/lib/slick/slick.min.css';
@import '../assets/lib/slick/slick-theme.min.css';
/* 轮播图 */
.banner.slick-dotted, .banner.slick-slider {
    margin-bottom: 0!important;
}
.banner.big img {
    height: 200px!important;
}
.slick-dots{
    bottom: 0px;
}
.slick-dots li{
    margin: 0px;
}
</style>

