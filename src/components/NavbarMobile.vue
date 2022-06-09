<template>
  <nav class="navbar-mobile d-flex flex-column align-items-center">
    <img class="navbar-mobile__logo col-8" src="../assets/logoMob.gif" alt="" />
    <p class="navbar__title text-start text-sm-center">
      MUSEO <span>de</span> PICHILEMU EN LINEA
    </p>
    <p class="navbar__url text-start col-12 text-sm-center">
      www.museopichilemuenlinea.cl
    </p>
    <p
      class="navbar__punchline text-start me-md-5 me-lg-auto col-12 text-sm-center mb-5"
    >
      Deuncuantohay
    </p>
    <button @click="riseIndex"  class="navbar-mobile__btn mt-5"><img src="../assets/search.svg" alt="" srcset=""></button>
  </nav>
</template>

<script>
export default {
  name: "NavbarMobile",
  emits: ["rise:index"],
  methods: {
    emitRiseIndex: function () {
      this.$emit("rise:index");
    },
    riseIndex: function () {
      console.log("hola");
      document
        .querySelector(".main .navbar-mobile")
        .classList.add("mobile-navbar--vanish");
      document.querySelector(".main .FAB").classList.add("show-FAB");
      document.querySelector(".main .FAB").classList.remove("d-none");
    },
  },
};
</script>

<style>
.navbar-mobile {
  font-family: "Old Standard TT", serif;
  height: 100vh;
  text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.1);
  text-align: center;
}
.navbar-mobile__btn {
  background-color: transparent;
  border: none;
}
.navbar-mobile .navbar__title {
  font-size: 40px;
  font-weight: 700;
  line-height: 34px;
  margin-top: 20px;
  margin-bottom: 0px;
}
.navbar-mobile .navbar__title span {
  font-style: italic;
}
.navbar-mobile .navbar__url {
  font-family: "Roboto Mono", monospace;
  font-size: 14px;
  line-height: 18px;
}
.navbar-mobile .navbar__punchline {
  font-size: 30px;
  line-height: 24px;
  margin-bottom: 5px;
}
hr {
  margin: 4px;
  color: #1d1d1d;
  background-color: #1d1d1d;
  border: 1px solid;
  opacity: 1;
}

</style>
