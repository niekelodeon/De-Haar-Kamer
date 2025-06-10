<template>

  <Head>
    <Title>De Haarkamer - Producten</Title>

    <link rel="canonical" href="https://www.de-haarkamer.nl/producten"/>
  </Head>

  <div class="root">

    <HeaderComponent/>

      <main>

        <div class="container-producten">

            <div class="container-photo" v-if="afbeeldingen && afbeeldingen.producten && afbeeldingen.producten[2].link !== ''">
              <img :src="afbeeldingen && afbeeldingen.producten && afbeeldingen.producten[2].link">
            </div>

            <div class="container-text-mobile">
              <p>{{ producten && producten.producten && producten.producten[0].tekst }}</p>
            </div>

            <div class="container-photo" v-if="afbeeldingen && afbeeldingen.producten && afbeeldingen.producten[3].link !== ''">
              <img :src="afbeeldingen && afbeeldingen.producten && afbeeldingen.producten[3].link">
            </div>

            <div class="container-photo" v-if="afbeeldingen && afbeeldingen.producten && afbeeldingen.producten[4].link !== ''">
              <img :src="afbeeldingen && afbeeldingen.producten && afbeeldingen.producten[4].link">
            </div>

            <div class="container-photo" v-if="afbeeldingen && afbeeldingen.producten && afbeeldingen.producten[5].link !== ''">
              <img :src="afbeeldingen && afbeeldingen.producten && afbeeldingen.producten[5].link">
            </div>
            
            <div class="container-photo" v-if="afbeeldingen && afbeeldingen.producten && afbeeldingen.producten[6].link !== ''">
              <img :src="afbeeldingen && afbeeldingen.producten && afbeeldingen.producten[6].link">
            </div>

        </div>

      </main>

    <BottomComponent/>

    <a class="whatsapp" href="https://wa.me/31653970234" target="_blank">
      <img class="whatsapp-img" src="../assets/whatsapp.png" alt="wa">
    </a>

    </div>

</template>

<script setup>
const { firstPending, data: producten } = useFetch('https://www.de-haarkamer.nl/data/producten.json', {
  server: false
})

const { secondPending, data: afbeeldingen } = useFetch('https://www.de-haarkamer.nl/data/afbeeldingen.json', {
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
/* Main */

main {
  position: relative;
  top: -70px;

  animation: fade-in 1.0s
}

.container-producten {
  display: flex;
  flex-direction: column;
  gap: 50px;

  padding-top: 10px;
  padding-bottom: 150px;
  padding-inline: 5%;

  animation: fade-in 1.0s
}

.container-text-mobile {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

@media (min-width: 450px) {
  .container-text-mobile {
    padding-inline: 50px;
  } 
}

.container-photo > img {
  border-radius: 0.5rem;
  height: auto;
  width: 100%;
  object-fit: cover;
}

.desktop-main {
  display: none;
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