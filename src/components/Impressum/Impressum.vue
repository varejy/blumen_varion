<template>
  <div class="impressum">
    <div class="container grayColorText">
      <div class="titleImpressum blackColorText">Impressum</div>
      <div class="headerImpress">
        <div class="headerImpressLeftItems">
          <div class="headerImpressItem impressumItem">
            <p>Carpe Diem Blumen und Ambiente GmbH & Co.KG</p>
            <br />
            <p>47709 Krefeld · Lessing Str. 50</p>
            <br />
            <p>
              Telefon: 02151/57 99 66 2 <br />
              Telefax: 0 21 51 / 57 99 66 4
            </p>
            <br />
            <p>E-Mail: carpe-diem@blumen-ambiente.eu</p>
            <br />
            <p>Geschäftsführer: Hildegard Peerenboom,</p>
            <p>Amtsgericht Krefeld: HRB 11263,</p>
            <p>Umsatzsteuer-Identifikationsnummer: 117/5702/0574,</p>
            <p>InhaltlichVerantwortlicher: Hildegard Peerenboom</p>
          </div>

          <div class="bodyImpressum">
            <div class="bodyImpressumItem impressumItem">
              <b class="blackColorText">Haftung für Inhalte</b> <br />
              Die Inhalte unserer Seiten wurden mit größter Sorgfalt erstellt.
              Für die Richtigkeit, Vollständigkeit und Aktualität der Inhalte
              können wir jedoch keine Gewähr übernehmen. Als Diensteanbieter
              sind wir gemäß § 7 Abs.1 TMG für eigene Inhalte auf diesen Seiten
              nach den allgemeinen Gesetzen verantwortlich. Nach §§ 8 bis 10 TMG
              sind wir als Diensteanbieter jedoch nicht verpflichtet,
              übermittelte oder gespeicherte fremde Informationen zu überwachen
              oder nach Umständen zu forschen, die auf eine rechtswidrige
              Tätigkeit hinweisen. Verpflichtungen zur Entfernung oder Sperrung
              der Nutzung von Informationen nach den allgemeinen Gesetzen
              bleiben hiervon unberührt. Eine diesbezügliche Haftung ist jedoch
              erst ab dem Zeitpunkt der Kenntnis einer konkreten
              Rechtsverletzung möglich. Bei Bekanntwerden von entsprechenden
              Rechtsverletzungen werden wir diese Inhalte umgehend entfernen.
            </div>
            <div class="bodyImpressumItem impressumItem">
              <b class="blackColorText">Haftung für Links</b> <br />
              Unser Angebot enthält Links zu externen Webseiten Dritter, auf
              deren Inhalte wir keinen Einfluss haben. Deshalb können wir für
              diese fremden Inhalte auch keine Gewähr übernehmen. Für die
              Inhalte der verlinkten Seiten ist stets der jeweilige Anbieter
              oder Betreiber der Seiten verantwortlich. Die verlinkten Seiten
              wurden zum Zeitpunkt der Verlinkung auf mögliche Rechtsverstöße
              überprüft. Rechtswidrige Inhalte waren zum Zeitpunkt der
              Verlinkung nicht erkennbar. Eine permanente inhaltliche Kontrolle
              der verlinkten Seiten ist jedoch ohne konkrete Anhaltspunkte einer
              Rechtsverletzung nicht zumutbar. Bei Bekanntwerden von
              Rechtsverletzungen werden wir derartige Links umgehend entfernen.
            </div>
          </div>
        </div>
        <div class="headerImpressItem impressumItem headerImpressRightItems">
          <b class="blackColorText">Urheberrecht</b> <br />
          Die durch die Seitenbetreiber erstellten Inhalte und Werke auf diesen
          Seiten unterliegen dem deutschen Urheberrecht. Die Vervielfältigung,
          Bearbeitung, Verbreitung und jede Art der Verwertung außerhalb der
          Grenzen des Urheberrechtes bedürfen der schriftlichen Zustimmung des
          jeweiligen Autors bzw. Erstellers. Downloads und Kopien dieser Seite
          sind nur für den privaten, nicht kommerziellen Gebrauch gestattet.
          Soweit die Inhalte auf dieser Seite nicht vom Betreiber erstellt
          wurden, werden die Urheberrechte Dritter beachtet. Sollten Sie
          trotzdem auf eine Urheberrechtsverletzung aufmerksam werden, bitten
          wir um einen entsprechenden Hinweis. Bei Bekanntwerden von
          Rechtsverletzungen werden wir derartige Inhalte umgehend entfernen.
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Impressum",
};
</script>

<style scoped>
.impressum {
  padding-top: 40px;
  padding-bottom: 40px;
  -webkit-animation-name: upItems;
  animation-name: upItems;
}

.headerImpress {
  display: flex;
  justify-content: space-between;
}

.titleImpressum {
  margin-bottom: 30px;
  font-size: 2rem;
  text-align: left;
}

.blackColorText {
  color: #212529;
}

.impressumItem {
  text-align: left;
  max-width: 554px;
  margin-bottom: 1rem;
}

.headerImpressRightItems {
  margin-left: 32px;
}

@media (max-width: 599px) {
  .headerImpress {
    display: block;
  }
  .headerImpressRightItems {
    margin-left: 0px;
  }
}
</style>
