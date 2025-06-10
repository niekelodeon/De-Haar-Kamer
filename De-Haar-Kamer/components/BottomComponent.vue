<template>

  <div class="container-bottom">

    <div class="socials">

      <a :href="algemeen && algemeen.instagram && algemeen.instagram[0].link">
        <img src="../assets/instagram.png" alt="instagram">
      </a>

      <a :href="algemeen && algemeen.facebook && algemeen.facebook[0].link">
        <img src="../assets/facebook.png" alt="facebook">
      </a>

    </div>

    <div class="copyright">
      <p id="copyright" class="copyright">&copy; {{ currentYear }} De Haarkamer</p>
    </div>

  </div>

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
      isActive: false,
      currentYear: new Date().getFullYear()
    }
  }
}
</script>

<style>
@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.container-bottom {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 15px;

  padding-bottom: 2rem;

  animation: fade-in 2.2s;
}

.socials {
  display: flex;
  gap: 15px;
}

a > img {
  width: 33px;
  height: 33px;
}

.copyright > p {
  color: #b59558;

  font-size: 16px;
}

@media (min-width: 650px) {
  .container-bottom {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 15px;

    padding-bottom: 2rem;
  }

  .socials {
    display: flex;
    gap: 15px;
  }

  a > img {
    width: 37px;
    height: 37px;
  }

  .copyright > p {
    color: #b59558;

    font-size: 18px;
  }
}
</style>


