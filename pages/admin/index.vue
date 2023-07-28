<template>
    <div class="landing-page">
        Ini halaman admin
    </div>
  </template>
  
  <script>
  export default {
    async asyncData({ $axios }) {
      const products = await $axios.$get('/api/v1/products')
      console.log(products)
      return { products }
    },
  }
  </script>
  
  <style lang="scss">
  .header__bg {
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    width: 100%;
    height: 640px;
    background-image: url('/auth-background.svg');
    background-position: top right;
    background-repeat: no-repeat;
    background-color: #3b41e3;
    transform: skewY(-6deg);
    transform-origin: top left;
  }
  
  .cta-clip {
    position: relative;
    top: 200px;
    bottom: 0;
    right: 0;
    left: 0;
    width: 100%;
    height: 300px;
    background-position: top right;
    background-size: 300px;
    background-repeat: no-repeat;
    background-color: #fff;
    transform: skewY(4deg);
    transform-origin: bottom right;
  }
  
  .call-to-action {
    background-image: url('/auth-background.svg');
    background-position: top right;
    background-repeat: no-repeat;
    background-size: 450px;
  }
  
  .card-project {
    transition: all 0.3s ease 0s, opacity 0.5s cubic-bezier(0.5, 0, 0, 1) 1ms;
    max-height: 485px;
    overflow: hidden;
  
    .button-cta {
      opacity: 0;
      transition: all 300ms ease;
    }
  
    &:hover {
      box-shadow: 0 4px 25px 0 rgba(0, 0, 0, 0.15);
  
      .button-cta {
        opacity: 1;
        transition: all 300ms ease;
      }
  
      .progress-bar,
      .progress-info {
        opacity: 0;
        height: 0px;
        margin: 0px;
        padding: 0px;
        transition: all 300ms ease;
      }
    }
  }
  
  footer {
    z-index: inherit;
  }
  
  .hero-underline {
    text-decoration-color: #1abc9c;
  }
  
  .testimonial-user {
    opacity: 0.4;
    &.active {
      opacity: 1;
      border: 5px solid #fff;
      box-shadow: 0 0 0 1px #3b41e3;
    }
  }
  </style>
  