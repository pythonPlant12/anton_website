<template>
    <header>
      <!-- ! Navigation Bar MOBILE-->
      <div class="container">
        <nav class="nav">
          <ul class="nav-list nav-list-mobile">
            <li class="nav-item">
              <div class="mobile-menu">
                <span class="line line-top"></span>
                <span class="line line-buttom"></span>
              </div>
            </li>
            <li class="nav-item">
              <a href="#" class="nav-link nav-link-apple"></a>
            </li>
            <li class="nav-item">
              <a href="#" class="nav-link nav-link-bag"></a>
            </li>
          </ul>
          <!-- /.nav-list nav-list-mobile -->
          <!-- ! Navigation List of Options Bar COMPUTER -->
          <ul class="nav-list nav-list-larger larger-mobile">
            <li class="nav-item nav-item-hidden">
              <div class="mobile-menu">
                <span class="line line-top"></span>
                <span class="line line-bottom"></span>
              </div>
            </li>
            <li class="nav-item">
              <a href="#" class="nav-link"></a>
            </li>
            <li class="nav-item">
              <a href="#" class="nav-link">Mac</a>
            </li>
            <li class="nav-item">
              <a href="#" class="nav-link">iPad</a>
            </li>
            <li class="nav-item">
              <a href="#" class="nav-link">iPhone</a>
            </li>
            <li class="nav-item">
              <a href="#" class="nav-link">Watch</a>
            </li>
            <li class="nav-item">
              <a href="#" class="nav-link">TV</a>
            </li>
            <li class="nav-item">
              <a href="#" class="nav-link">Support</a>
            </li>
            <li class="nav-item">
              <a href="#" class="nav-link nav-link-search"></a>
            </li>
            <li class="nav-item nav-item-hidden">
              <a href="#" class="nav-link nav-link-bag"></a>
            </li>
          </ul>
        </nav>
      </div>
    </header>
    <slot />
    </template>
  
  <style>
  a {
    display: block;
    text-decoration: none;
  }
  /* ! Header */
  header {
    display: flex; /* Use flexbox */
    justify-content: center; /* Center horizontally */
    align-items: center; /* Center vertically */
    position: fixed;
    top: 0;
    z-index: 14;
    width: 100%;
    height: 4.4rem;
    background-color: rgba(0, 0, 0, 0.5);
    backdrop-filter: blur(2rem);
  }
  
  .nav-list {
    list-style: none;
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 0 -1rem;
  }
  
  .nav-list-mobile {
    display: none;
  }
  
  .nav-link {
    font-size: 1.4rem;
    color: #fff;
    padding: 0 1rem;
    transition: opacity 0.5s;
  }
  .nav-link:hover {
    opacity: 0.7;
  }
  
  .nav-link-apple {
    align-self: center;
    width: 1.6rem;
    height: 4.4rem;
    background: url("~/assets/css/icons/apple.svg") center no-repeat;
  }
  
  .nav-link-search {
    width: 1.6rem;
    height: 4.4rem;
    background: url("~/assets/css/icons/search.svg") center no-repeat;
  }
  
  .nav-link-bag {
    margin-right: 2rem;
    align-self: center;
    width: 1.4rem;
    height: 4.4rem;
    background: url("~/assets/css/icons/bag.svg") center no-repeat;
  }
  
  @media screen and (max-width: 1068px) {
    .hero {
      height: 100rem;
      background-size: auto 100rem;
      background-position: bottom center;
      background-repeat: no-repeat;
    }
    header {
      display: block; /* Use flexbox */
    }
    .title-heading {
      font-size: 4.4rem;
    }
  
    .title-sub-heading {
      font-size: 2.4rem;
      color: white;
    }
  
    .cta-link:nth-child(2) {
      margin-left: 2rem;
    }
  
    .title-heading-watch {
      height: 6.2rem;
      /* background-image: url("images/hero/watch/logo_watch_medium.png"); */
      background-size: auto 6.2rem;
    }
  }
  
  /* ! CSS Styles for PHONE (Small Screen ) */
  @media screen and (max-width: 735px) {
    header {
      height: 4.8rem;
      transition: background 0.36s cubic-bezier(0.32, 0.08, 0.24, 1),
        height 0.56s cubic-bezier(0.32, 0.08, 0.24, 1);
    }
  
    header .container {
      padding: 0;
    }
  
    .iphone-11-pro {
      margin-top: 4.8rem;
    }
  
    .nav-list {
      margin-top: 0;
    }
  
    .nav-list-mobile {
      display: flex;
    }
  
    .nav-item {
      width: 4.8rem;
      height: 4.8rem;
      display: flex;
      justify-content: center;
    }
    .nav-item-hidden {
      display: none;
    }
  
    /* ! Lines of mobile menu trigger */
    .mobile-menu {
      margin-left: 2rem;
      position: relative;
      z-index: 15;
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      cursor: pointer;
    }
  
    .line {
      position: absolute;
      width: 1.7rem;
      height: 1px;
      background-color: #fff;
      transition: margin-top 0.3192s cubic-bezier(0.04, 0.04, 0.12, 0.96);
    }
  
    .line-top {
      margin-bottom: 10px;
    }
    .line-buttom {
      margin-top: -0.4px;
    }
    /* ! Mobile Menu Trigger transition/transform */
  
    .active .line-top {
      margin-bottom: 0;
      transform: rotate(45deg);
      transition: transform 0.3192s 0.1s cubic-bezier(0.04, 0.04, 0.12, 0.96);
    }
    .active .line-buttom {
      margin-top: 0;
      transform: rotate(-45deg);
      transition: transform 0.3192s 0.1s cubic-bezier(0.04, 0.04, 0.12, 0.96);
    }
  
    header.active {
      height: 100%;
      background-color: rgba(0, 0, 0, 0.8);
      backdrop-filter: blur(2rem);
    }
  
    .nav-link-apple {
      width: 1.8rem;
      height: 4.8rem;
      position: relative;
      z-index: 15;
    }
  
    .nav-link-bag {
      width: 1.6rem;
      height: 4.8rem;
      transition: opacity 3s;
    }
  
    .nav {
      position: relative;
    }
  
    .nav-link {
      font-size: 1.7rem;
      padding: 0;
      margin: auto 0;
    }
  
    .nav-list-larger {
      position: fixed;
      opacity: 0;
      /* ! */
      visibility: hidden;
      top: 0;
      left: 0;
      width: 0;
      height: 0;
      display: block;
      padding: 10.5rem 5rem;
      z-index: 10;
      box-sizing: border-box;
      transition: opacity 0.3s;
    }
  
    .active .nav-link-bag {
      opacity: 0;
      transition: opacity 0.3s;
    }
  
    .nav-list-larger .nav-item {
      width: 100%;
      justify-content: flex-start;
      border-bottom: 2px solid rgba(255, 255, 255, 0.1);
    }
    .nav-list-larger .nav-item:nth-child(9) {
      border-bottom: none;
    }
  }
  .active .nav-list-larger .nav-item {
    opacity: 1;
  }
  .active .nav-list-larger {
    animation: fadeIn 1s ease-in;
    opacity: 1;
    width: 100%;
    height: 100vh;
    visibility: visible;
  }
  @keyframes fadeIn {
    from {
      opacity: 0;
      visibility: hidden;
    }
    to {
      opacity: 1;
      visibility: visible;
    }
  }
  </style>
  <script>
export default {
  mounted() {
    const selectElement = (element) => document.querySelector(element);

    selectElement(".mobile-menu").addEventListener("click", () => {
      selectElement("header").classList.toggle("active");
    });
  },
};
  </script>
  