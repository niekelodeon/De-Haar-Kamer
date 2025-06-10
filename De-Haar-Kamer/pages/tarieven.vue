<template>

  <Head>
    <Title>De Haarkamer - Tarieven</Title>

    <link rel="canonical" href="https://www.de-haarkamer.nl/tarieven"/>
  </Head>

  <div class="root">

    <HeaderComponent /> 

    <main>

      <div class="container">

        <h1>{{ tarieven && tarieven.titel && tarieven.titel[0].name }}</h1>

          <div class="container-pricing">

            <div class="price-1" v-if="tarieven && Object.keys(tarieven)[1]">
              <span class="title">{{ Object.keys(tarieven)[1] }}</span>
              <div class="service" v-for="tarief in tarieven[Object.keys(tarieven)[1]]" :key="tarief.name">
                <span class="service-name">{{ tarief.name }}</span>
                <span class="service-voor">{{ tarief.voor ? tarief.voor + ' ' : '' }}</span>
                <span class="service-cur">{{ tarief.price ? '€' : '' }}</span>
                <span class="service-price">{{ tarief.price }}</span>
              </div>
            </div>
      
            <div class="price-2" v-if="tarieven && Object.keys(tarieven)[2]">
              <span class="title">{{ Object.keys(tarieven)[2] }}</span>
              <div class="service" v-for="tarief in tarieven[Object.keys(tarieven)[2]]" :key="tarief.name">
                <span class="service-name">{{ tarief.name }}</span>
                <span class="service-voor">{{ tarief.voor ? tarief.voor + ' ' : '' }}</span>
                <span class="service-cur">{{ tarief.price ? '€' : '' }}</span>
                <span class="service-price">{{ tarief.price }}</span>
              </div>
            </div>

            <div class="price-3" v-if="tarieven && Object.keys(tarieven)[3]">
              <span class="title">{{ Object.keys(tarieven)[3] }}</span>
              <div class="service" v-for="tarief in tarieven[Object.keys(tarieven)[3]]" :key="tarief.name">
                <span class="service-name">{{ tarief.name }}</span>
                <span class="service-voor">{{ tarief.voor ? tarief.voor + ' ' : '' }}</span>
                <span class="service-cur">{{ tarief.price ? '€' : '' }}</span>
                <span class="service-price">{{ tarief.price }}</span>
              </div>
            </div>

            <div class="price-4" v-if="tarieven && Object.keys(tarieven)[4]">
              <span class="title">{{ Object.keys(tarieven)[4] }}</span>
              <div class="service" v-for="tarief in tarieven[Object.keys(tarieven)[4]]" :key="tarief.name">
                <span class="service-name">{{ tarief.name }}</span>
                <span class="service-voor">{{ tarief.voor ? tarief.voor + ' ' : '' }}</span>
                <span class="service-cur">{{ tarief.price ? '€' : '' }}</span>
                <span class="service-price">{{ tarief.price }}</span>
              </div>
            </div>

            <div class="price-5" v-if="tarieven && Object.keys(tarieven)[5]">
              <span class="title">{{ Object.keys(tarieven)[5] }}</span>
              <div class="service" v-for="tarief in tarieven[Object.keys(tarieven)[5]]" :key="tarief.name">
                <span class="service-name">{{ tarief.name }}</span>
                <span class="service-voor">{{ tarief.voor ? tarief.voor + ' ' : '' }}</span>
                <span class="service-cur">{{ tarief.price ? '€' : '' }}</span>
                <span class="service-price">{{ tarief.price }}</span>
              </div>
            </div>

            <div class="price-6" v-if="tarieven && Object.keys(tarieven)[6]">
              <span class="title">{{ Object.keys(tarieven)[6] }}</span>
              <div class="service" v-for="tarief in tarieven[Object.keys(tarieven)[6]]" :key="tarief.name">
                <span class="service-name">{{ tarief.name }}</span>
                <span class="service-voor">{{ tarief.voor ? tarief.voor + ' ' : '' }}</span>
                <span class="service-cur">{{ tarief.price ? '€' : '' }}</span>
                <span class="service-price">{{ tarief.price }}</span>
              </div>
            </div>

            <div class="price-7" v-if="tarieven && Object.keys(tarieven)[7]">
              <span class="title">{{ Object.keys(tarieven)[7] }}</span>
              <div class="service" v-for="tarief in tarieven[Object.keys(tarieven)[7]]" :key="tarief.name">
                <span class="service-name">{{ tarief.name }}</span>
                <span class="service-voor">{{ tarief.voor ? tarief.voor + ' ' : '' }}</span>
                <span class="service-cur">{{ tarief.price ? '€' : '' }}</span>
                <span class="service-price">{{ tarief.price }}</span>
              </div>
            </div>

            <div class="price-8" v-if="tarieven && Object.keys(tarieven)[8]">
              <span class="title">{{ Object.keys(tarieven)[8] }}</span>
              <div class="service" v-for="tarief in tarieven[Object.keys(tarieven)[8]]" :key="tarief.name">
                <span class="service-name">{{ tarief.name }}</span>
                <span class="service-voor">{{ tarief.voor ? tarief.voor + ' ' : '' }}</span>
                <span class="service-cur">{{ tarief.price ? '€' : '' }}</span>
                <span class="service-price">{{ tarief.price }}</span>
              </div>
            </div>

            <div class="price-9" v-if="tarieven && Object.keys(tarieven)[9]">
              <span class="title">{{ Object.keys(tarieven)[9] }}</span>
              <div class="service" v-for="tarief in tarieven[Object.keys(tarieven)[9]]" :key="tarief.name">
                <span class="service-name">{{ tarief.name }}</span>
                <span class="service-voor">{{ tarief.voor ? tarief.voor + ' ' : '' }}</span>
                <span class="service-cur">{{ tarief.price ? '€' : '' }}</span>
                <span class="service-price">{{ tarief.price }}</span>
              </div>
            </div>

            <div class="price-10" v-if="tarieven && Object.keys(tarieven)[10]">
              <span class="title">{{ Object.keys(tarieven)[10] }}</span>
              <div class="service" v-for="tarief in tarieven[Object.keys(tarieven)[10]]" :key="tarief.name">
                <span class="service-name">{{ tarief.name }}</span>
                <span class="service-voor">{{ tarief.voor ? tarief.voor + ' ' : '' }}</span>
                <span class="service-cur">{{ tarief.price ? '€' : '' }}</span>
                <span class="service-price">{{ tarief.price }}</span>
              </div>
            </div>

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
const { pending, data: tarieven } = useFetch('https://www.de-haarkamer.nl/data/tarieven.json', {
  server: false
});

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
  top: -100px;

  animation: fade-in 1.0s
}
.container {
  display: flex;
  flex-direction: column;

  padding-top: 10px;
  padding-inline: 2%;
}

@media (min-width: 420px) {
  .container {
    padding-inline: 5%;
  }
}

@media (min-width: 470px) {
  .container {
    padding-inline: 7%;
  }
}

.container > h1 {
  display: flex;
  justify-content: center;

  padding-top: 25px;
  padding-bottom: 25px;
}

.container-pricing {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 50px;
}

.container-pricing > h1 {
  display: flex;
  justify-content: center;

  padding-top: 25px;
  padding-bottom: 25px;
}

.title {
  display: flex;
  justify-content: center;
    
  margin-bottom: 20px;

  font-weight: 600;
}

.service {
  display: flex;
  flex-direction: row;
  justify-content: space-between;

  gap: 20px;

  margin-bottom: 3px;
}

.service-price {
  display: flex;
  justify-content: center;
  align-items: center;

  white-space: nowrap;
}

.service-voor, .service-cur {
  position: absolute;
}

/* Currency Signs */

@media (min-width: 350px) {
  .service-cur {
    left: 80%;
  }

  .service-voor {
    left: 72%;
  }
}

@media (min-width: 360px) {
  .service-cur {
    left: 79%;
  }

  .service-voor {
    left: 71%;
  }
}

@media (min-width: 370px) {
  .service-cur {
    left: 78.9%;
  }

  .service-voor {
    left: 70.9%;
  }
}

@media (min-width: 380px) {
  .service-cur {
    left: 79.5%;
  }

  .service-voor {
    left: 71.9%;
  }
}

@media (min-width: 390px) {
  .service-cur {
    left: 80.1%;
  }

  .service-voor {
    left: 72.9%;
  }
}

@media (min-width: 400px) {
  .service-cur {
    left: 80.7%;
  }

  .service-voor {
    left: 73.9%;
  }
}

@media (min-width: 420px) {
  .service-cur {
    left: 79.5%;
  }

  .service-voor {
    left: 73.2%;
  }
}

@media (min-width: 520px) {
  .service-cur {
    left: 80.5%;
  }

  .service-voor {
    left: 74.8%;
  }
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

@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>