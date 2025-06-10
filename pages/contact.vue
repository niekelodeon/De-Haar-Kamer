<template>

  <Head>
    <Title>De Haarkamer - Contact</Title>

    <link rel="canonical" href="https://www.de-haarkamer.nl/contact"/>
  </Head>

  <div class="root">

    <HeaderComponent/>

    <main>

      <div class="container-contact">

        <div class="container-photo" v-if="afbeeldingen && afbeeldingen.contact && afbeeldingen.contact[0].link !== ''">
          <img :src="afbeeldingen && afbeeldingen.contact && afbeeldingen.contact[0].link">
        </div>

        <div class="contact" v-if="contact && Object.keys(contact)[0]">
          <h1>{{ Object.keys(contact)[0] }}</h1>
          <span class="info-item-1" v-for="items in contact[Object.keys(contact)[0]]" :key="contact.name">{{ items.item }}</span>
        </div>

        <div class="openhours" v-if="contact && Object.keys(contact)[1]">
          <h1>{{ Object.keys(contact)[1] }}</h1>
          <span class="info-item-2" v-for="items in contact[Object.keys(contact)[1]]" :key="contact.name">{{ items.item }}</span>
        </div>

        <div class="container-photo" v-if="afbeeldingen && afbeeldingen.contact && afbeeldingen.contact[1].link !== ''">
          <img :src="afbeeldingen && afbeeldingen.contact && afbeeldingen.contact[1].link">
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
const { firstpending, data: contact } = useFetch('https://www.de-haarkamer.nl/data/contact.json', {
  server: false
})

const { secondpending, data: afbeeldingen } = useFetch('https://www.de-haarkamer.nl/data/afbeeldingen.json', {
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
main {
  position: relative;
  top: -80px;

  animation: fade-in 1.0s
}

.container-contact {
  display: flex;
  flex-direction: column;
  gap: 50px;

  padding-inline: 5%;
  padding-top: 25px;
  padding-bottom: 100px;
}

.contact {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.contact > h1 {
  display: flex;
  align-items: center;
  justify-content: center;

  text-align: center;
  margin-bottom: 20px;

  color: #9e711e;
}

.contact > span {
  margin-bottom: 3px;
}

.contact > .info-item-1:nth-child(4) {
  margin-bottom: 20px;
}

.openhours {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.openhours > span {
  margin-bottom: 3px;
}

.openhours > h1 {
  display: flex;
  align-items: center;
  justify-content: center;

  text-align: center;
  margin-bottom: 20px;

  color: #9e711e;
}

.container-photo > img {
  border-radius: 0.5rem;
  height: auto;
  width: 100%;
  object-fit: cover;
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