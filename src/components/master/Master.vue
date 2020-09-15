<template>
  <div>
    <home></home>
    <about></about>
    <service></service>
    <portfolio></portfolio>
    <pricing></pricing>
    <contact-us></contact-us>
  </div>
</template>

<script>
import Home from '../home/Home.vue'
import About from '../about/About.vue'
import Service from '../service/Service.vue'
import Portfolio from '../portfolio/Portfolio.vue'
import Pricing from '../pricing/Pricing.vue'
import Contact from '../contact/Contact.vue'

export default {
  // data () {

  // },
  components: {
    'home': Home,
    'about': About,
    'service': Service,
    'portfolio': Portfolio,
    'pricing': Pricing,
    'contact-us': Contact
  },
  mounted () {
    // :: 4.0 SCROLL TO TOP ACTIVE CODE
    var offset = 300
    var duration = 500
    $(window).on('scroll', function () {
      if ($(this).scrollTop() > offset) {
        $('#scrollUp').fadeIn(duration)
      } else {
        $('#scrollUp').fadeOut(duration)
      }
    })

    $('#scrollUp').on('click', function () {
      $('html, body').animate({
        scrollTop: 0
      }, duration)
    })

    // :: 5.0 SCROLL LINK ACTIVE CODE
    var scrollLink = $('.scroll')

    // :: 6.0 SMOOTH SCROLLING ACTIVE CODE
    scrollLink.on('click', function (e) {
      e.preventDefault()
      $('body,html').animate({
        scrollTop: $(this.hash).offset().top
      }, 1000)
    })

    // :: 7.0 AOS ACTIVE CODE
    AOS.init()

    // :: 8.0 WOW ACTIVE CODE
    new WOW().init()

    // :: 9.0 PREVENT DEFAULT ACTIVE CODE
    $('a[href="#"]').on('click', function ($) {
      $.preventDefault()
    })

    // :: 10.0 COUNTERUP ACTIVE CODE
    // $('.counter').counterUp({
    //   delay: 10,
    //   time: 1000
    // })

    // :: 11.0 FANCYBOX VIDEO POPUP ACTIVE CODE
    // $('.play-btn').fancybox({
    //   animationEffect: 'zoom-in-out',
    //   transitionEffect: 'circular',
    //   maxWidth: 800,
    //   maxHeight: 600,
    //   youtube: {
    //     controls: 0
    //   }
    // })

    // :: 12.0 CIRCLE ANIMATION ACTIVE CODE
    $(window).on('load', function () {
      $('.profile-circle-wrapper').addClass('circle-animation')
      $('.profile-icon').fadeIn()
    })
  }
}
</script>

<style scoped></style>
