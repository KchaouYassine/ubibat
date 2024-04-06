<template>
  <div class="whoareWeSection container text-center my-5 ">
    <h1 class="sectionTitle text-orange fw-bold text-uppercase">About UBIBAT</h1>
    <div class="content text-center fs-5 fw-bold py-3">
      <p>UBIBAT est une entreprise spécialisée dans le domaine du calcul de structures, du
      diagnostic et de la reconnaissance des structures existantes et du suivi des chantiers.<br>
      Fondée par des ingénieurs spécialisés dans le domaine des calculs de structures, UBIBAT
      intervient sur plusieurs projets couvrant divers types d’ouvrages : bureaux, logements,
      bâtiments industriels universités, hôpitaux, usines, ouvrages d’art et génie civil…  <br>
      UBIBAT réalise les études préliminaires de faisabilité, études d’avant-projet, et les études
      d’exécution sur les projets neufs. <br>
      Dotée de matériels d’inspections et d’auscultation, la société UBIBAT réalise aussi les
      missions de diagnostics structurels avec les sondages de reconnaissances, les
      inspections périodiques, les préconisations sur les travaux de remise en état nécessaires
      avec une estimation financière des travaux . <br>
      Muni d’une expérience de plus que 4 ans sur le terrain, UBIBAT accompagne ses clients en
      phase d’exécution et assure les missions liées à la conduite des travaux.
      </p>
    </div>
      
      
  </div>
</template>

<style lang="scss">
.whoareWeSection{
  .content{
    line-height: 35px;
  }
}

.sectionTitle {
    font-size: 60px;
    position: relative;
    display: inline-block;
}

// TODO
.sectionTitle::before {
    position: absolute;
    content: "";
    width: 45px;
    height: 2px;
    top: 50%;
    left: -55px;
    margin-top: -1px;
    background: var(--primary);
}

.sectionTitle::after {
    position: absolute;
    content: "";
    width: 45px;
    height: 2px;
    top: 50%;
    right: -55px;
    margin-top: -1px;
    background: var(--primary);
}

</style>