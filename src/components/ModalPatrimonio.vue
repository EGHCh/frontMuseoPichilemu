<template>
  <div class="container-fluid patrimonio-modal mt-sm-5 fixed-bottom d-flex">
    <div class="modal-container py-4 px-2">
      <h3 class="modal-title">Qué entendemos por patrimonio cultural</h3>
      <hr />
      <p class="pb-4 px-sm-4">
        El <strong>patrimonio cultural</strong> es un conjunto determinado de bienes tangibles,
        intangibles y naturales que forman parte de prácticas sociales, a los
        que se les atribuyen valores a ser transmitidos, y luego resignificados,
        de una época a otra, o de una generación a las siguientes. Así, un
        objeto se transforma en patrimonio o bien cultural, o deja de serlo,
        mediante un proceso y/o cuando alguien -individuo o colectividad-,
        afirma su nueva condición (Dibam, Memoria, cultura y creación.
        Lineamientos políticos. Documento, Santiago, 2005).
        <br />
        <br />
        El hecho de que el patrimonio cultural se conforme a partir de un
        proceso social y cultural de atribución de valores, funciones y
        significados, implica que no constituye algo dado de una vez y para
        siempre sino, más bien, es <strong>el producto de un proceso social permanente,
        complejo y polémico, de construcción de significados y sentidos.</strong> Así,
        los objetos y bienes resguardados adquieren razón de ser en la medida
        que se abren a nuevos sentidos y se asocian a una cultura presente que
        los contextualiza, los recrea e interpreta de manera dinámica.
        <br />
        <br />
        El valor de dichos bienes y manifestaciones culturales no está en un
        pasado rescatado de modo fiel, sino en la relación que en el presente
        establecen las personas y las sociedades, con dichas huellas y
        testimonios. Por ello, los ciudadanos no son meros receptores pasivos
        sino sujetos que conocen y transforman esa realidad, posibilitando el
        surgimiento de nuevas interpretaciones y usos patrimoniales. Como la
        UNESCO ha subrayado, el término "patrimonio cultural" no siempre ha
        tenido el mismo significado, y en las últimas décadas ha experimentado
        un profundo cambio. Actualmente, ésta es una noción más abierta que
        también incluye expresiones de la cultura presente, y no sólo del
        pasado.
        <br />
        <br />
        Por otra parte, si en un momento dicho concepto estuvo referido
        exclusivamente a los monumentos, ahora ha ido incorporando,
        gradualmente, nuevas categorías tales como las de patrimonio intangible,
        etnográfico o industrial, las que, a su vez, han demandado nuevos
        esfuerzos de conceptualización. Junto con ello se ha otorgado mayor
        atención a las artes de la representación, lenguas y música tradicional,
        así como a los sistemas filosóficos, espirituales y de información que
        constituyen el marco de dichas creaciones.
        <br />

        Fuente: Servicio Nacional del Patrimonio Cultural
      </p>
      <button class="modal-close" @click="closeModal">
        <img src="../assets/close.png" alt="" />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalPatrimonio",
  methods: {
    closeModal: function () {
      document.querySelector(".patrimonio-modal").classList.add("d-none");
      document.querySelector(".patrimonio-modal").classList.remove("d-flex");
    },
  },
};
</script>

<style>
.patrimonio-modal {
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
.patrimonio-modal .modal-container {
  height: 70vh;
  max-width: 700px;
  background-image: url(https://images.unsplash.com/photo-1615800098779-1be32e60cca3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2020&q=80);
  background-attachment: fixed;
}
.modal-container .modal-title {
  font-size: 24px;
  font-weight: bold;
  line-height: 24px;
}
.modal-container p {
  max-height: 70%;
  overflow: scroll;
}
.modal-close {
  border: none;
  background: rgba(0, 0, 0, 0);
  margin-top: 1rem;
}
</style>
