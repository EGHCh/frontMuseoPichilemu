<template>
  <EditorialSection class="sticky-top d-sm-none editorial-for-mobile pt-2" />
  <!-- <div v-if="post.contenido">
    <ModalCard
      :modalSRC="post.imagen"
      :modalTitle="post.title.rendered"
      :modalBody="post.contenido"
      class=""
    />
  </div> -->
  <section class="gallery container-fluid d-flex">
    <div
      class="gallery__selector fixed-left gallery__selector--desktop gallery__selector--left d-flex flex-column mx-auto"
    >
      <a @click="getChoice(`2`)" value="2" class="text-center  mb-sm-0"
        >A</a
      >
      <a @click="getChoice(`17`)" class="text-center  mb-sm-0">B</a>
      <a @click="getChoice(``)" class="text-center  mb-sm-0">C</a>
      <a @click="getChoice(`66`)" class="text-center  mb-sm-0">D</a>
      <a @click="getChoice(`73`)" class="text-center  mb-sm-0">E</a>
      <a @click="getChoice(`80`)" class="text-center  mb-sm-0">F</a>
      <a @click="getChoice(`86`)" class="text-center  mb-sm-0">G</a>
      <a @click="getChoice(`99`)" class="text-center  mb-sm-0">H</a>
      <a @click="getChoice(`104`)" class="text-center  mb-sm-0">I</a>
      <a @click="getChoice(`109`)" class="text-center  mb-sm-0">J</a>
      <a @click="getChoice(``)" class="text-center  mb-sm-0">K</a>
      <a @click="getChoice(`116`)" class="text-center  mb-sm-0">L</a>
      <a @click="getChoice(`124`)" class="text-center  mb-sm-0">LL</a>
      <a @click="getChoice(`129`)" class="text-center  mb-sm-0">M</a>
    </div>
    <div
      @wheel="riseIndex"
      @scroll="riseIndex"
      class="gallery__display container gallery__grid ms-3 ms-sm-auto"
    >
      <CardTemplate
        v-for="(post, index) in posts"
        :key="index"
        :cardTitle="post.title.rendered"
        :cardBody="post.contenido"
        :picture_src="post.imagen"
        @click="getPost(post)"
      ></CardTemplate>
    </div>
    <div
      class="gallery__selector gallery__selector--desktop gallery__selector--right d-flex flex-column mb-auto mt-auto"
    >
      <a @click="getChoice(`145`)" class="text-center  mb-sm-0">N</a>
      <a @click="getChoice(``)" class="text-center  mb-sm-0">Ñ</a>
      <a @click="getChoice(`151`)" class="text-center  mb-sm-0">O</a>
      <a @click="getChoice(`154`)" class="text-center  mb-sm-0">P</a>
      <a @click="getChoice(``)" class="text-center  mb-sm-0">Q</a>
      <a @click="getChoice(`187`)" class="text-center  mb-sm-0">R</a>
      <a @click="getChoice(`198`)" class="text-center  mb-sm-0">S</a>
      <a @click="getChoice(`207`)" class="text-center  mb-sm-0">T</a>
      <a @click="getChoice(``)" class="text-center  mb-sm-0">U</a>
      <a @click="getChoice(`223`)" class="text-center  mb-sm-0">V</a>
      <a @click="getChoice(``)" class="text-center  mb-sm-0">W</a>
      <a @click="getChoice(``)" class="text-center  mb-sm-0">X</a>
      <a @click="getChoice(`235`)" class="text-center  mb-sm-0">Y</a>
      <a @click="getChoice(`237`)" class="text-center  mb-sm-0">Z</a>
    </div>
  </section>
</template>

<script>
import CardTemplate from "./card.vue";
import EditorialSection from "./editorialSection.vue";
// import ModalCard from "./ModalCard.vue";
export default {
  name: "Gallery-section",
  data() {
    return {
      choice: "",
      post: {},
    };
  },
  components: {
    CardTemplate,
    EditorialSection,
    // ModalCard,
  },
  props: {
    posts: Array,
    selectCategory: Function,
  },
  emits: ["update:choice", "update:modal"],
  setup() {},
  mounted() {},
  methods: {
    getChoice: function (choice) {
      this.$emit("update:choice", choice);
    },
    getPost: function (post) {
      this.post = post;
      this.$emit("update:modal", post);
      // document.querySelector(".card-modal").classList.add("d-flex");
      // document.querySelector(".card-modal").classList.remove("d-none");
    },
  },
};
</script>

<style>
CardTemplate {
  margin-bottom: 1rem;
}
.editorial-for-mobile {
  background-image: url(https://images.unsplash.com/photo-1615800098779-1be32e60cca3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2020&q=80);
  background-attachment: fixed;
  border-top: 1px solid black;
  border-bottom: 0;
}
.gallery__selector {
  font-family: "Old Standard TT", serif;
}
.gallery .gallery__selector {
  position: fixed;
}
.gallery__selector a {
  text-decoration: none;
  text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.2);
  color: #1d1d1d;
  font-size: 20px;
  width: 30px;
}
.gallery__selector a:hover {
  font-size: 24px;
  color: #1d1d1d;
}
.gallery__selector--left {
  border-right: 1.5px solid #1d1d1d;
  left: 0;
}
.gallery__selector--right {
  border-left: 1.5px solid #1d1d1d;
  right: 0;
}
.gallery .gallery__display {
  width: auto;
}
.gallery .gallery__grid {
  display: grid;
  grid-template-columns: 300px;
  grid-gap: 1rem;
}
/* BREAKPOINTS */
@media (min-width: 576px) {
  .gallery__selector a {
    font-size: 24px;
    width: 40px;
  }
  .gallery__selector a:hover {
    font-size: 28px;
    color: #1d1d1d;
  }
}
@media (min-width: 724px) {
  .gallery .gallery__grid {
    grid-template-columns: 300px 300px;
    margin-left: auto;
  }
}
@media (min-width: 999px) {
  .gallery .gallery__grid {
    grid-template-columns: 300px 300px 300px;
  }
}
@media (min-width: 1400px) {
  .gallery .gallery__grid {
    grid-template-columns: 300px 300px 300px 300px;
  }
}
</style>
