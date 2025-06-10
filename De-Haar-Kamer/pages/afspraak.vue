<template>

  <Head>
    <Title>De Haarkamer - Afspraak</Title>

    <link rel="canonical" href="https://www.de-haarkamer.nl/afspraak"/>
  </Head>

  <div class="root">

    <HeaderComponent />

    <main>

      <div class="container-afspraak">

        <div class="container-button">
          <a class="button-afspraak" v-if="algemeen && algemeen.knop && algemeen.knop[0].toggle === 'true' "
          :href="algemeen && algemeen.afspraak && algemeen.afspraak[0].link" @mouseenter="isHover = true"
          @mouseleave="isHover = false"
          :class="{ 'button-afspraak-hover': isHover }">Maak afspraak</a>
        </div>

      </div>

    </main>

    <BottomComponent />

    <a class="whatsapp" href="https://wa.me/31653970234" target="_blank">
      <img class="whatsapp-img" src="../assets/whatsapp.png" alt="wa">
    </a>

  </div>

</template>

<script setup>
const { pending, data: algemeen } = useFetch('https://www.de-haarkamer.nl/data/algemeen.json', {
  server: false
})

useHead({
  title: 'De Haarkamer',
})
</script>

<script>
export default {
  mounted() {
    this.handleScreenSize();
    window.addEventListener('resize', this.handleScreenSize);
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.handleScreenSize);
  },
  methods: {
    handleScreenSize() {
      if (window.innerWidth > 550) {
        this.$router.push('/');
      }
    }
  }
};
</script>

<style scoped>
@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

main {
  position: relative;
  top: -55px;

  animation: fade-in 1.0s
}

.container-afspraak {
  display: flex;
  flex-direction: column;
  gap: 50px;

  padding-inline: 5%;
  padding-top: 100px;
  padding-bottom: 225px;
}

.container-button {
  display: flex;
  justify-content: center;
}

.container-afspraak > span {
  display: flex;
  align-items: center;
  justify-content: center;

  text-align: center;

  padding-inline: 50px;
}

.button-afspraak {
  font-size: 16px;
  font-weight: 600;

  padding: 15px 25px;
  border-radius: 0.5em;

  border: none;
  text-align: center;
  text-decoration: none;

  color: #000;
}

.button-afspraak {
  transition: background-color 0.3s;
  background-color: #DCAD70;
}

.button-afspraak-hover {
  background-color: #e6c07b;
}

/* Animation */

@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* Whatsapp Button */

.whatsapp {
  z-index: 99;

  animation: fade-in 0.5s;
}

.whatsapp-img {
  width: 55px;
  height: 55px;

  position: fixed;
  right: 30px;
  bottom: 40px;

  border-radius: 40px;

  transition: transform 0.5s;

  z-index: 99;
}

.whatsapp-img:hover {
  transform: scale(1.2);
  transition: 0.3s linear;
}

@media (min-width: 550px) {
  .whatsapp-img {
    width: 60px;
    height: 60px;

    right: 45px;
    bottom: 45px;
  }
}
</style>