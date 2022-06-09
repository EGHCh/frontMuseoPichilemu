<template>
  <div class="container-fluid editorial-modal mt-sm-5 fixed-bottom d-flex">
    <div class="modal-container py-4 px-2">
      <h3 class="modal-title">EDITORIAL</h3>
      <hr />
      <p class="pb-4 px-sm-4">
        Un museo (del latín, musēum y este, a su vez, del griego, Μουσείον) es
        una institución pública o privada, permanente, con o sin fines de lucro,
        al servicio de la sociedad y de su desarrollo, y abierta al público, que
        adquiere, conserva, investiga, comunica, expone o exhibe, con propósitos
        de estudio y educación, colecciones de arte, científicas, entre otros,
        siempre con un valor cultural, según el Consejo Internacional de Museos
        (ICOM).2 La ciencia que los estudia se denomina museología, la técnica
        de su gestión museografía y la administración de los mismos, museonomía.
        <br/>
        <br/>
        Los museos exponen colecciones, es decir, conjuntos de objetos e
        información que reflejan algún aspecto de la existencia humana o su
        entorno. Este tipo de colecciones, casi siempre valiosas, existen desde
        la Antigüedad: en los templos se guardaban objetos de culto u ofrendas
        que de vez en cuando se exhibían al público para que pudiera
        contemplarlos y admirarlos. Lo mismo ocurría con los objetos valiosos y
        obras de arte que coleccionaban algunas personas de la aristocracia en
        Grecia y en Roma; los tenían expuestos en sus casas, en sus jardines y
        los enseñaban con orgullo a los amigos y visitantes. Fue en el
        Renacimiento cuando se dio el nombre de "museo" tal y como hoy se
        entiende a los edificios expresamente dedicados la conservación y
        exposición de sus colecciones permanentes. Por otra parte están las
        galerías de arte, donde se muestran pinturas y esculturas, en
        exposiciones temporales, sin que necesariamente posean colecciones
        permanentes. Su nombre deriva de las galerías (de los palacios y
        castillos), que eran los espaciosos vestíbulos de forma alargada, con
        muchas ventanas o abiertos y sostenidos por columnas o pilares,
        destinados a los momentos de descanso y a la exhibición de objetos de
        adorno, muchas veces obras de arte.
        <br/>
        <br/>
        Después de la Primera Guerra Mundial
        (1918) surgió la Oficina Internacional de Museos, que articuló los
        criterios museográficos cuyos programas y soluciones técnicas son
        vigentes hoy en día. En 1945 nació el Consejo Internacional de Museos
        (ICOM, por sus siglas en inglés) y en 1948 aparece la publicación
        periódica Museum mediante la cual se difunden hasta hoy en día las
        actividades de los museos en el mundo. (Fuente: Párrafos de la
        descripción de Wikipedia..).
      </p>
      <button class="modal-close" @click="closeModal">
        <img src="../assets/close.png" alt="" />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalEditorial",
  methods: {
    closeModal: function () {
      document.querySelector(".editorial-modal").classList.add("d-none");
      document.querySelector(".editorial-modal").classList.remove("d-flex");
    },
  },
};
</script>

<style>
.editorial-modal {
  box-sizing: border-box;
  top: 0;
  width: 100vw;
  height: 100vh;
  z-index: 1999;
  background-color: rgba(0, 0, 0, 0.5);
  align-items: center;
  justify-content: center;
  font-family: "Old Standard TT", serif;
}
.editorial-modal .modal-container {
  height: 70vh;
  max-width: 700px;
  background-image: url(https://images.unsplash.com/photo-1615800098779-1be32e60cca3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2020&q=80);
  background-attachment: fixed;
}
.editorial-modal .modal-container .modal-title {
  font-size: 24px;
  font-weight: bold;
  line-height: 24px;
}
.editorial-modal .modal-container p {
  max-height: 70%;
  overflow: scroll;
}
.editorial-modal .modal-close {
  border: none;
  background: rgba(0, 0, 0, 0);
  margin-top: 1rem;
}
</style>
