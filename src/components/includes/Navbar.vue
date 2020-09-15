<template>
  <div>
    <header id="header">
      <nav data-aos="zoom-out" data-aos-delay="800" class="navbar navbar-expand">
        <div class="container header">
          <a class="navbar-brand" href="index.html">
            <img class="navbar-brand-regular" src="../../../static/assets/img/logo/logo-white.png" alt="brand-logo">
            <img class="navbar-brand-sticky" src="../../../static/assets/img/logo/logo.png" alt="sticky brand-logo">
          </a>
          <div class="ml-auto"></div>
          <ul class="navbar-nav items">
            <li class="nav-item">
              <a class="nav-link scroll" href="#home">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link scroll" href="#about">About</a>
            </li>
            <li class="nav-item">
              <a class="nav-link scroll" href="#services">Services</a>
            </li>
            <li class="nav-item">
              <a class="nav-link scroll" href="#portfolio">Portfolio</a>
            </li>
            <li class="nav-item">
              <a class="nav-link scroll" href="#pricing">Pricing</a>
            </li>
            <li class="nav-item">
              <a class="nav-link scroll" href="#contact">Contact</a>
            </li>
          </ul>
          <ul class="navbar-nav icons">
            <li class="nav-item">
              <a href="#" class="nav-link" data-toggle="modal" data-target="#search">
                <i class="fas fa-search"></i>
              </a>
            </li>
            <li class="nav-item social">
              <a href="#" class="nav-link"><i class="fab fa-facebook-f"></i></a>
            </li>
            <li class="nav-item social">
              <a href="#" class="nav-link"><i class="fab fa-twitter"></i></a>
            </li>
          </ul>

          <ul class="navbar-nav toggle">
            <li class="nav-item">
              <a href="#" class="nav-link" data-toggle="modal" data-target="#menu">
                <i class="fas fa-bars toggle-icon m-0"></i>
              </a>
            </li>
          </ul>

          <ul class="navbar-nav action">
            <li class="nav-item ml-3">
              <a href="#" class="btn ml-lg-auto btn-bordered-white"><i class="fas fa-paper-plane contact-icon mr-md-2"></i>Contact Us</a>
            </li>
          </ul>
        </div>
      </nav>
    </header>
  </div>
</template>

<script>
export default {
  mounted () {
    var zero = 0
    function navResponsive () {
      let navbar = $('.navbar .items')
      let menu = $('#menu .items')
      menu.html('')
      navbar.clone().appendTo(menu)
      $('.menu .fa-angle-right').removeClass('fa-angle-right').addClass('fa-angle-down')
    }
    navResponsive()
    $(window).on('resize', function () {
      navResponsive()
    })
    // PREVENT DROPDOWN
    $('.menu .dropdown-menu').each(function () {
      var children = $(this).children('.dropdown').length
      $(this).addClass('children-' + children)
    })
    $('.menu .nav-item.dropdown').each(function () {
      var children = $(this).children('.nav-link')
      children.addClass('prevent')
    })
    $(document).on('click', '#menu .nav-item .nav-link', function (e) {
      if ($(this).hasClass('prevent')) {
        e.preventDefault()
      }
      var navNlink = $(this)
      navNlink.next().toggleClass('show')
      if (navNlink.hasClass('smooth-anchor')) {
        $('#menu').modal('hide')
      }
    })
    // :: 3.0 STICKY HEADER ACTIVE CODE
    $(window).on('scroll', function () {
      if ($(window).scrollTop() > 100) {
        $('.navbar').addClass('navbar-sticky')
        $('.navbar .navbar-nav.action .btn').addClass('btn-bordered')
        $('.navbar .navbar-nav.action .btn').removeClass('btn-bordered-white')
      } else {
        $('.navbar').removeClass('navbar-sticky')
        $('.navbar .navbar-nav.action .btn').removeClass('btn-bordered')
        $('.navbar .navbar-nav.action .btn').addClass('btn-bordered-white')
      }
    })
    $(window).on('scroll', function () {
      $('.navbar-sticky').toggleClass('hide', $(window).scrollTop() > zero)
      zero = $(window).scrollTop()
    })
  }
}
</script>

<style scoped>
  .navbar {
    opacity: 1;
  }
</style>
