<template>

  <div class="container-top">

    <!-- Desktop -->
    <img class="logo-desktop" src="../assets/logo-desktop.gif" alt="Animation" id="gif">

    <!-- Mobile -->
    <img class="logo-mobile" :class="{'fade-in': isPageLoaded}" src="../assets/logo-mobile.gif" alt="Animation" id="gif">

  </div>

  <div class="hamburger-container">
    <button class="hamburger" :class="{ 'is-active': isActive }" @click="toggleMenu">
      <div class="bar"></div>
    </button>
  </div>

  <transition name="fade">
    <nav v-if="isActive" class="mobile-nav" ref="mobileNav" :class="{ 'is-active': isActive }" :style="{ overflow: isActive ? 'hidden' : 'auto' }">
      <div class="links">
        <NuxtLink to="/" exact class="nav-link" active-class="link-active">Home</NuxtLink>
        <NuxtLink to="/tarieven" exact class="nav-link" active-class="link-active">Tarieven</NuxtLink>
        <NuxtLink to="/afspraak" exact class="nav-link" active-class="link-active" v-if="algemeen && algemeen.knop && algemeen.knop[0].toggle === 'true'">Maak afspraak</NuxtLink>
        <NuxtLink to="/producten" exact class="nav-link" active-class="link-active">Producten</NuxtLink>
        <NuxtLink to="/contact" exact class="nav-link" active-class="link-active">Contact</NuxtLink>
      </div>
    </nav>
  </transition>

</template>

<script setup>
const { firstPending, data: algemeen } = useFetch('https://www.de-haarkamer.nl/data/algemeen.json', {
  server: false
});
</script>

<script>
export default {
  data() {
    return {
      isActive: false
    }
  },

  mounted () {
    // Menu Closes New Page

    this.$router.afterEach(() => {
      this.closeMenu();
    }); 
  },

  methods: {
    toggleMenu() {
      this.isActive = !this.isActive;
      document.body.style.overflow = this.isActive ? 'hidden' : 'auto';
      window.scrollTo(0, 0);
    },
    closeMenu() {
      this.isActive = false;
      document.body.style.overflow = 'auto';
      window.scrollTo({ top: 0 });
    }
  }
}
</script> 

<style>
/* Navigation Menu Animations */

@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes fade-out {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}

.logo-desktop {
  display: none;
}

.logo-mobile {
  display: flex;

  position: relative;
  right: 2px;
  top: -30px;

  margin: 0 auto;
  z-index: -99;
}

.mobile-nav {
  display: none;

  background-color: #F8F7F4;

  position: fixed;
  top: 175px;
  width: 100%;
  min-height: 100vh;

  z-index: 99;
}

.mobile-nav.is-active {
  display: block;
}

.fade-enter-active {
  animation: fade-in 0.7s;
}

.fade-leave-active {
  animation: fade-out 0.7s;
}   

.mobile-nav > .links {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 40px;

  padding-top: 65px;
}

.nav-link {
  font-size: 18px;
  text-decoration: none;

  color: #313131;
}

.link-active {
  font-size: 18px;
  text-decoration: none;

  color: #B59558;
}

.mobile-nav-second > .a-active {
  color: var(--main-green)
}

.logo-mobile {
  max-width: 100%;
  height: 280px;
}

/* Hamburger Menu */

.hamburger {
  position: absolute;
  top: 0;
  right: 0;

  width: 33px;
  margin-top: 57px;
  margin-right: 30px;

  cursor: pointer;
  appearance: none;
  background: none;
  outline: none;
  border: none;

  animation: fade-in 1.5s;
}

/* Hamburger Menu Margin-right */

@media (min-width: 390px) { 
  .hamburger {
    margin-right: 35px;
  }
}

@media (min-width: 410px) { 
  .hamburger {
    margin-right: 50px;
  }
}

@media (min-width: 435px) { 
  .hamburger {
    margin-right: 60px;
  }
}

@media (min-width: 455px) { 
  .hamburger {
    margin-right: 70px;
  }
}

@media (min-width: 475px) { 
  .hamburger {
    margin-right: 80px;
  }
}

@media (min-width: 495px) { 
  .hamburger {
    margin-right: 90px;
  }
}

@media (min-width: 515px) { 
  .hamburger {
    margin-right: 100px;
  }
}

@media (min-width: 535px) { 
  .hamburger {
    margin-right: 110px;
  }
}

.hamburger.is-active > .bar {
  background-color: var(--main-orange);

  transform: translate(15px, 0); 
  transition: 0.4s all ease-in-out;
}

.hamburger.is-active::before {
  transform: rotate(-45deg) translate(-8px, 5px);
}

.hamburger.is-active::after {
  transform: rotate(45deg) translate(-9px, -6px);
}

.bar, .hamburger::after, .hamburger::before {
  content: '';
  display: block;
  transition: 0.3s;

  width: 100%;
  height: 4px;

  margin: 6px 0px;
    
  background-color: #B59558;
}

.hamburger.is-active .bar {
  opacity: 0;
}

@media (min-width: 550px) {
  .logo-mobile {
    display: none;
  }

  .hamburger {
    display: none;
  }

  /* Turning Menu Off */

  .mobile-nav {
    display: none;
  }

  .mobile-nav.is-active {
    display: none;
  }

  .logo-desktop {
    display: flex;

    margin: 0 auto;

    position: relative;
    top: -40px;
    right: 3px;

    border: none;
    outline: none;
    -webkit-playsinline: true;

    animation: fade-in 2s;
  }
}

/* Resizing Logo */

@media (min-width: 550px) {
  .logo-desktop {
    width: 550px;
    height: 309.19px;
  }
}

@media (min-width: 600px) {
  .logo-desktop {
    width: 575px;
    height: 323.24px;
  }
}

@media (min-width: 650px) {
  .logo-desktop {
    width: 625px;
    height: 351.35px;
  }
}

@media (min-width: 700px) {
  .logo-desktop {
    width: 675px;
    height: 379.46px;
  }
}

@media (min-width: 740px) {
  .logo-desktop {
    width: 740px;
    height: 416px;
  }
}

/* Header Logo */

.container-top {
  display: flex;
  justify-content: center;

  z-index: -99;
}
</style>