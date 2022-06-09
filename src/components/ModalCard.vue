<template>
  <div class="container-fluid card-modal mt-sm-5 fixed-bottom">
    <div class="bg-image">
      <img :src="modalSRC" class="img-fluid" />
      <div class="mask " style="background-color: rgba(0, 0, 0, 0.5)">
        <div class="text container-fluid d-flex flex-column">
          <div class="overflow-scroll pt-2">
            <h3 class="modal-title">{{ modalTitle }}</h3>
            <hr />
            <p class="pb-4 px-sm-4">
              {{ modalBody }}
            </p>
          </div>
          <button class="modal-close" @click="closeModal">
            <img src="../assets/closeCard.png" alt="" />
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalCard",
  emits: [],
  props: {
    modalSRC: String,
    modalTitle: String,
    modalBody: String,
  },
  methods: {
    closeModal: function () {
      document.querySelector(".card-modal").classList.add("d-none");
      document.querySelector(".card-modal").classList.remove("d-flex");
    },
  },
};
</script>

<style>
.card-modal {
  box-sizing: border-box;
  top: 0;
  width: 100vw;
  height: 100vh;
  z-index: 1999;
  position: relative;
  /* top: -7%; */
  display: flex;
  background-color: rgba(0, 0, 0, 0.5);
  align-items: center;
  justify-content: center;
  font-family: "Roboto Mono", monospace;
}

.card-modal .modal-img {
  position: relative;
  width: 100%;
}
.modal-img img {
  border-radius: 0 0 10px 0;
}
.modal-container .body-container {
  height: auto;
}
.body-container--background {
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 10px;
  width: 100%;
  z-index: 2;
  position: relative;
  top: auto;
}
.modal-container .card {
  height: 70vh;
}
.card-modal .modal-container {
  height: 70vh;
  max-width: 80%;
  border-radius: 10px;
  background-color: rgb(233, 138, 21);
  background-attachment: fixed;
  overflow: hidden;
}
.card-modal .modal-title {
  font-size: 30px;
  font-weight: bold;
  line-height: 24px;
}
.card-modal .modal-container p {
  /* max-height: 70%; */
  font-size: 24px;
}
.card-modal .modal-close {
  border: none;
  background: rgba(0, 0, 0, 0);
  /* position: absolute; */
  bottom: -3rem;
}
/* CARD OVERLAY */
.bg-image {
  position: relative;
  overflow: hidden;
  background-repeat: no-repeat;
  background-size: cover;
  max-height: 70vh;
  max-width: 90vw;
  border-radius: 10px;
}

.bg-image img {
  max-height: 70vh;
  max-width: 90vw;
}

.bg-image .mask {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
  color: #fff;
}

.bg-image .mask .text {
  height: 100%;
  display: flex !important;
  /* align-items: space-around !important; */
  justify-content: end !important;
}

.bg-image .mask .text p {
  margin: 0;
}

@media (min-width: 400px) {
  .card-modal .modal-close {
    position: static;
  }
  .bg-image {
      max-width: 90vw;
  }
}
</style>
