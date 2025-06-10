<template>

  <div class="root">

    <!-- Meta Tags -->
    <Head>
      <Title>De Haarkamer</Title>

      <Meta name="description" content="Een fijne dames & heren kapper in Wemeldinge. Wij zijn gespecialiseerd in knippen, kleuren en wassen. Graag sta ik voor u klaar met persoonlijk en professioneel advies. Tot snel in De Haarkamer!"/>
      <Meta name="viewport" content="width=device-width, initial-scale=1"/>
      <Meta name="keywords" content="kapper, kapster, wemeldinge, knippen, kleuren, verven, afspraak, dames, heren, kinderen"/>
      <Meta name="category" content="kapper"/>
      <Meta name="robots" content="index, follow"/>
      <Meta name="revisit-after" content="2 days"/>
      <Meta name="og:title" content="De Haarkamer"/>
      <Meta name="og:description" content="Een fijne dames & heren kapper in Wemeldinge. Wij zijn gespecialiseerd in knippen, kleuren en wassen. Graag sta ik voor u klaar met persoonlijk en professioneel advies. Tot snel in De Haarkamer!"/>
      <Meta name="og:region" content="Wemeldinge"/>

      <Link rel="canonical" href="https://www.de-haarkamer.nl/"/>
      <Link rel="icon" href="favicon.ico" type="image/x-icon"/>

      <Meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate"/>
      <Meta http-equiv="Pragma" content="no-cache"/>
      <Meta http-equiv="Expires" content="0"/>
    </Head>

    <HeaderComponent />

    <main>

      <div class="mobile-main">

        <div class="container-photo">
          <img :src="afbeeldingen && afbeeldingen.home && afbeeldingen.home[0].link">
        </div>

        <div class="container-text-mobile">
          <p>{{ algemeen && algemeen.tekst_mobile && algemeen.tekst_mobile[0].tekst }}</p>
        </div>

        <div class="container-photo">
          <img :src="afbeeldingen && afbeeldingen.home && afbeeldingen.home[1].link">
        </div>

      </div>

      <div class="desktop-main">

        <div class="row-1">

          <div class="boxOne">
            <img :src="afbeeldingen && afbeeldingen.home && afbeeldingen.home[0].link">
          </div>

          <div class="boxTwo">
            <div class="container-afspraak">

              <p>{{ algemeen && algemeen.tekst && algemeen.tekst[0].tekst }}</p>

              <div class="container-button">
                <a class="button-afspraak" v-if="algemeen && algemeen.knop && algemeen.knop[0].toggle === 'true' "
                :href="algemeen && algemeen.afspraak && algemeen.afspraak[0].link" @mouseenter="isHover = true"
                @mouseleave="isHover = false"
                :class="{ 'button-afspraak-hover': isHover }">Maak afspraak</a>
              </div>

            </div>
          </div>

        </div>

        <div class="row-2">

          <div class="boxThree">

            <h1>{{ tarieven && tarieven.titel && tarieven.titel[0].name }}</h1>

            <div class="container-grid">

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

        </div>

        <div class="row-3">

          <div class="boxFour">
            <img :src="afbeeldingen && afbeeldingen.home && afbeeldingen.home[1].link">
          </div>

          <div class="boxFive">
            
            <div class="container-contact">

              <div class="contact" v-if="contact && Object.keys(contact)[0]">
                <h1>{{ Object.keys(contact)[0] }}</h1>
                <span class="info-item-1" v-for="items in contact[Object.keys(contact)[0]]" :key="contact.name">{{ items.item }}</span>
              </div>

              <div class="openhours" v-if="contact && Object.keys(contact)[1]">
                <h1>{{ Object.keys(contact)[1] }}</h1>
                <span class="info-item-2" v-for="items in contact[Object.keys(contact)[1]]" :key="contact.name">{{ items.item }}</span>
              </div>

            </div>

          </div>

        </div>

        <div class="row-4">

          <div class="boxSix">
            
            <div class="container-products">

              <div class="container-image">
                <img :src="afbeeldingen && afbeeldingen.producten && afbeeldingen.producten[0].link">
                <img :src="afbeeldingen && afbeeldingen.producten && afbeeldingen.producten[1].link">
              </div>

              <div class="container-text">
                <h1>{{ producten && producten.titel && producten.titel[0].name }}</h1>

                <p>{{ producten && producten.producten && producten.producten[0].tekst }}</p>
              </div>

            </div>

          </div>

        </div>

      </div>

    </main>

    <BottomComponent />

    <a class="whatsapp" :href="algemeen && algemeen.whatsapp && algemeen.whatsapp[0].link" target="_blank">
      <img class="whatsapp-img" src="../assets/whatsapp.png" alt="wa">
    </a>

  </div>

</template>

<script setup>
const { firstPending, data: tarieven } = useFetch('https://www.de-haarkamer.nl/data/tarieven.json', {
  server: false
})

const { secondPending, data: contact } = useFetch('https://www.de-haarkamer.nl/data/contact.json', {
  server: false
})

const { thirdPending, data: algemeen } = useFetch('https://www.de-haarkamer.nl/data/algemeen.json', {
  server: false
})

const { fourthPending, data: producten } = useFetch('https://www.de-haarkamer.nl/data/producten.json', {
  server: false
})

const { fifthPending, data: afbeeldingen } = useFetch('https://www.de-haarkamer.nl/data/afbeeldingen.json', {
  server: false
})

useHead({
  title: 'De Haarkamer',
})
</script>

<script>
export default {
  data() {
    return {
      isActive: false,
      isHover: false,
      currentYear: new Date().getFullYear()
    }
  },
}
</script>

<style scoped>
/* Main */

main {
  position: relative;
  top: -70px;

  animation: fade-in 1.0s
}

.mobile-main {
  position: relative;
  top: -10px;

  display: flex;
  flex-direction: column;
  gap: 50px;

  padding-top: 10px;
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
    padding-inline: 10px;
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

@media (min-width: 550px) {
  main {
    position: relative;
    top: -90px;
  }

  .mobile-main {
    display: none;
  }

  .desktop-main {
    display: flex;
    flex-direction: column;
    gap: 5em;

    padding-inline: 5%;
  }
}

@media (min-width: 650px) {
  main {
    position: relative;
    top: -90px;
  }
}

/* row-1 > boxOne Foto & boxTwo Afspraak */

.row-1 {
  display: flex;
  flex-direction: column;
  gap: 5em;
}

@media (min-width: 1500px) {
  .row-1 {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 5em;
  }
}

.boxOne {
  display: flex;
  justify-content: center;
  align-items: center;

  height: 20rem;
  border-radius: 0.5rem;

  animation: fade-in 1s;
}

.boxOne > img {
  border-radius: 0.5rem;
  height: auto;
  width: 100%;
  object-fit: cover;
}

.boxTwo {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  animation: fade-in 2s;

  height: 20rem;
}

@media (min-width: 1000px) {
  .boxOne, .boxTwo {
    height: 30rem;
  }
}

.container-afspraak {
  display: flex;
  flex-direction: column;
  gap: 50px;

  padding-inline: 100px;
}

.container-button {
  display: flex;
  justify-content: center;
}

.container-afspraak {
  display: flex;
  align-items: center;
  justify-content: center;

  text-align: center;

  padding-inline: 100px;
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

@media (min-width: 800px) {
  .container-afspraak {
    padding-inline: 200px;
  }
}

@media (min-width: 1000px) {
  .container-afspraak {
    padding-inline: 200px;
  }
}

@media (min-width: 1100px) {
  .container-afspraak {
    padding-inline: 300px;
  }
}

@media (min-width: 1300px) {
  .container-afspraak {
    padding-inline: 400px;
  }
}

@media (min-width: 1400px) {
  .container-afspraak {
    padding-inline: 500px;
  }
}

@media (min-width: 1500px) {
  .container-afspraak {
    padding-inline: 100px;
  }
}

/* row-2 > boxThree Tarieven */

.row-2 {

}

.boxThree {
  border-radius: 0.5rem;

  animation: fade-in 2s;
}

.boxThree > h1 {
  display: flex;
  justify-content: center;

  padding-top: 25px;
  padding-bottom: 25px;
}

@media (min-width: 1000px) {
  .boxThree {
    min-height: 30rem;
  }

  .boxThree > h1 {
    padding-top: 50px;
    padding-bottom: 50px;
  }
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

.container-grid {
  display: flex; 
  flex-direction: column;
  gap: 30px;

  padding-inline: 30px;
  padding-bottom: 25px;
}

/* Grid Layout Tarieven */

@media (min-width: 950px) {
  .container-grid {
    display: grid; 
    grid-template-columns: 0.5fr 0.5fr; 
    gap: 2em 5em; 
    grid-template-areas: 
      ". ."
      ". ."
      ". ."
      ". ."; 

    padding-inline: 50px;
    padding-bottom: 50px;
  }
}

@media (min-width: 1000px) {
  .container-grid {
    display: grid; 
    grid-template-columns: 0.5fr 0.5fr; 
    gap: 2em 5em; 
    grid-template-areas: 
      ". ."
      ". ."
      ". ."
      ". ."; 

    padding-inline: 50px;
    padding-bottom: 75px;
  }

  .container-grid > * {
    margin-bottom: 30px;
  }
}

@media (min-width: 1100px) {
  .container-grid {
    padding-inline: 100px;
  }
}

@media (min-width: 1400px) {
  .container-grid {
    display: grid; 
    grid-template-columns: 0.5fr 0.5fr; 
    gap: 2em 7em; 
    grid-template-areas: 
      ". ."
      ". ."
      ". ."
      ". ."; 

    padding-inline: 150px;
    padding-bottom: 75px;
  }
}

@media (min-width: 1850px) {
  .container-grid {
    display: grid; 
    grid-template-columns: 0.5fr 0.5fr; 
    gap: 2em 7em; 
    grid-template-areas: 
      ". ."
      ". ."
      ". ."
      ". ."; 

    padding-inline: 400px;
    padding-bottom: 75px;
  }
}

@media (min-width: 2000px) {
  .container-grid {
    display: grid; 
    grid-template-columns: 0.5fr 0.5fr; 
    gap: 2em 7em; 
    grid-template-areas: 
      ". ."
      ". ."
      ". ."
      ". ."; 

    padding-inline: 500px;
    padding-bottom: 75px;
  }
}

/* .row-3 > boxFour Foto & boxFive Contact, Openingstijden */

.row-3 {
  display: flex;
  flex-direction: column;
  grid-template-columns: 2fr 1fr;
  gap: 5em;
}

@media (min-width: 1500px) {
  .row-3 {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 5em;
  }
}

.boxFour {
  display: flex;
  justify-content: center;
  align-items: center;

  height: 20rem;
  border-radius: 0.5rem;

  animation: fade-in 1s;
}

.boxFour > img {
  border-radius: 0.5rem;
  height: auto;
  width: 100%;
  object-fit: cover;
}

.boxFive {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 50px;

  height: 20rem;
  border-radius: 0.5rem;
}

@media (min-width: 1000px) {
  .boxFour, .boxFive {
    height: 30rem;
  }
}

.container-contact {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 50px;
}

@media (min-width: 1500px) {
  .container-contact {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 50px;
  }
}

.contact, .openhours {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.contact > h1 {
  margin-bottom: 20px;
}

.openhours > h1 {
  margin-bottom: 20px;
}

.info-item-1, .info-item-2 {
  margin-bottom: 3px;
}

.info-item-1:nth-child(4) {
  margin-bottom: 20px;
}

.adres, .contact {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

/* row-4 > boxSix Producten */

.boxSix {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 50px;

  height: 25rem;
  border-radius: 0.5rem;

  /* margin-top: 5em; */
}

@media (min-width: 1000px) {
  .boxSix {
    height: 30rem;
  }
}

.container-products {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 30px;
}

.container-text {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  text-align: center;
  gap: 20px;

  padding-inline: 10%;
}

.container-products > .container-image {
  display: flex;
  flex-direction: row;
  gap: 70px;
}

.container-products {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 30px;
}

.container-text {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  text-align: center;
  gap: 20px;

  padding-inline: 10%;
}

.container-products > .container-image {
  display: flex;
  flex-direction: row;
  gap: 70px;
}

.container-image img:nth-child(2) {
  display: none;
}


@media (min-width: 750px) {
  .boxSix {
    padding-inline: 5%;
  }

  .container-products {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 10px;
  }

  .container-products > .container-image {
    display: flex;
    flex-direction: row;
    gap: 0px;
  }

  .container-text {
    display: flex;
    flex-direction: column;
    align-items: start;
    gap: 20px;

    text-align: left;

    padding-inline: 0%;
  }
}

@media (min-width: 800px) {
  .container-products {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 30px;
  }

  .container-products > .container-image {
    display: flex;
    flex-direction: row;
    gap: 0px;
  }

  .container-text {
    display: flex;
    flex-direction: column;
    gap: 20px;

    padding-right: 0px;
  }
}

@media (min-width: 1200px) {
  .container-products {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 30px;
  }

  .container-products > .container-image {
    display: flex;
    flex-direction: row;
    gap: 0px;
  }

  .container-image img:nth-child(2) {
    display: flex;
  }

  .container-text {
    display: flex;
    flex-direction: column;
    gap: 20px;

    padding-right: 0px;
  }
}

@media (min-width: 1400px) {
  .container-products {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 75px;
  }

  .container-products > .container-image {
    display: flex;
    flex-direction: row;
    gap: 40px;
  }

  .container-text {
    display: flex;
    flex-direction: column;
    gap: 20px;

    padding-right: 70px;
  }
}

@media (min-width: 1600px) {
  .container-products {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 75px;
  }

  .container-text {
    display: flex;
    flex-direction: column;
    gap: 20px;

    padding-right: 150px;
  }
}

@media (min-width: 1800px) {
  .container-products {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 100px;
  }

  .container-text {
    display: flex;
    flex-direction: column;
    gap: 20px;

    padding-right: 250px;
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