<template>
  <div id="app">
    <NavbarComponent/>
    <router-view />
    <FooterComponent />
  </div>
</template>

<script>
import $ from 'jquery';
import NavbarComponent from './components/NavbarComponent'
import FooterComponent from './components/FooterComponent.vue';

export default {
  name: 'App',
  components: {
    NavbarComponent,
    FooterComponent
},
  created(){
    $(window).scroll(function (){
      if($(this).scrollTop() > 20){
          $('.back-to-top').fadeIn('slow');
      }else{
        $('.back-to-top').fadeOut('slow');
      }
    });
    $('.back-to-top').click(function(){
      $('html, body').animate({scrollTop:0}, 1500, 'easeInOutExpo');
      return false;
    })
  }
}
</script>

<style>

</style>
