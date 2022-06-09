<template>
  <main class="container-fluid main">
    <!-- Modals -->
    <ModalPatrimonio class="d-none" />
    <ModalEditorial class="d-none" />
    <div v-if="post.contenido" class="fixed-bottom">
      <ModalCard
        :modalSRC="post.imagen"
        :modalTitle="post.title.rendered"
        :modalBody="post.contenido"
      />
    </div>
    <!-- Site Body -->
    <!-- <NavbarComponent
      @scroll="riseIndex"
      class="d-sm-none p-0 mb-0 mobile-navbar"
    >
    </NavbarComponent> -->
    <FAB @click="backToTheNavbar" />
    <NavbarMobile class="d-sm-none" @rise:index="riseIndex" />
    <NavbarComponent class="fixed-top d-none d-sm-flex" />
    <GallerySection
      :posts="data"
      @update:modal="modalUpdate"
      @update:choice="choiceUpdate"
    ></GallerySection>
    <!-- @update:post="modalUpdateNShow" -->
    <FooterComponent></FooterComponent>
  </main>
</template>

<script>
import axios from "axios";
import NavbarComponent from "./components/navbar.vue";
import NavbarMobile from "./components/NavbarMobile.vue";
import GallerySection from "./components/gallery.vue";
import FooterComponent from "./components/footerComponent.vue";
import FAB from "./components/FAB.vue";
import ModalPatrimonio from "./components/ModalPatrimonio.vue";
import ModalEditorial from "./components/ModalEditorial.vue";
import ModalCard from "./components/ModalCard.vue";

//const baseURL =
//  "http://wsgnoticias.byethost7.com/wp-json/wp/v2/posts?secciones=";

export default {
  name: "App",
  components: {
    NavbarComponent,
    NavbarMobile,
    GallerySection,
    FooterComponent,
    FAB,
    ModalPatrimonio,
    ModalEditorial,
    ModalCard,
  },
  data() {
    return {
      data: [],
      choice: "",
      postForModal: {},
      showModal: null,
      post: {},
    };
  },
  mounted() {
    axios
      .get("https://backendmuseopichilemu.com/wp-json/wp/v2/posts?per_page=40")
      .then((data) => (this.data = data.data));
  },
  methods: {
    riseIndex: function () {
      console.log("hola");
      document
        .querySelector(".main .navbar-mobile")
        .classList.add("mobile-navbar--vanish");
      document.querySelector(".main .FAB").classList.add("show-FAB");
      document.querySelector(".main .FAB").classList.remove("d-none");
    },
    backToTheNavbar: function () {
      document
        .querySelector(".main .navbar-mobile")
        .classList.remove("mobile-navbar--vanish");
      document.querySelector(".main .FAB").classList.add("d-none");
      window.scrollTo(0, 0);
    },
    choiceUpdate: function (value) {
      console.log(value);
      axios
        .get(
          "https://backendmuseopichilemu.com/wp-json/wp/v2/posts?categories=" +
            value
        )
        .then((resp) => (this.data = resp.data))
        .then(console.log(value.target))
        .catch((err) => console.log(err));
      // fetch("http://backendmuseopichilemu.com/wp-json/wp/v2/posts").then(response => response.json()).then(data => (this.data = data.data)).then(console.log(this.data))
    },
    modalUpdate: function (post) {
      this.post = post;
      console.log(post);
      document.querySelector(".card-modal").classList.add("d-flex");
      document.querySelector(".card-modal").classList.remove("d-none");
    },
    // modalUpdateNShow: function (post) {
    //   this.postForModal = post;
    //   console.log(this.postForModal);
    // },
  },
};
</script>
<style>
.mobile-navbar {
  height: 80vh;
  animation: vanish-header 3s ease;
}
.main .mobile-navbar--vanish {
  height: 0vh;
  opacity: 0;
  top: -75vh;
  animation: riseGallery 2s ease;
}

@keyframes riseGallery {
  from {
    height: 30vh;
    opacity: 0.5;
  }
  to {
    height: 0vh;
    top: -30vh;
    opacity: 0;
  }
}
</style>
