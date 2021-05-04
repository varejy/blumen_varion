<template>
  <section class="section static">
    <div class="static-container section">
      <div class="container">
        <div class="static-container-wrap">
          <div class="static-columns">
            <div class="static-column grayColorText">
              <h2>Liebe Kunden</h2>

              <p>
                Leidenschaft und Tradition verpflichten. Seit Jahrzehnten sind
                wir stolz auf die Hochwertigkeit unserer Blumen und Pflanzen.
                Für Ihre blumigen Wünsche stehen unsere Floristen mit Erfahrung
                und handwerklicher Kreativität zur Seite.
              </p>

              <p>Unsere Schwerpunkte:</p>

              <p>
                <strong
                  >Brautschmuck, Tischschmuck, Trauerfloristik, Wohnambiente,
                  Fleurop-Service&nbsp;&amp;&nbsp;Lieferservice</strong
                >
              </p>

              <p>
                Der Einkauf bei regionalen Erzeugern ermöglicht uns höchste
                Qualität und Frische zu gewährleisten.
              </p>

              <p>
                <strong>Öffnungszeiten:</strong>&nbsp;Mo-Fr: 8.30 &nbsp;–
                18.30,&nbsp;Sa: 8.30 – 16.00,&nbsp;So: 10.00 – 12.00
              </p>

              <p><strong>Besondere Öffnungszeiten:&nbsp;</strong></p>

              <ul class="workTime">
                <li>Ostersonntag 10:00 – 13:00</li>
                <li>Samstag vor Muttertag 08:00 – 18:00</li>
                <li>Muttertag 08:00 &nbsp;– 14:00</li>
                <li>Pfingstsonntag&nbsp; 10:00 – 13:00</li>
                <li>Heiligabend 07:00 – 14:00</li>
                <li>1. Weihnachtstag 10:00 – 12:00</li>
                <li>Silvester 08:00 – 13:00</li>
                <li>Neujahr 10:00 – 12:00<br /></li>
              </ul>

              <p>Rufen Sie uns einfach an unter:<br />02151/57 99 66 2</p>

              <p>
                Oder schreiben Sie uns eine E-Mail an:<br />
                <a class="mail" href="mailto:carpe-diem@blumen-ambiente.eu"
                  >carpe-diem@blumen-ambiente.eu</a
                >
              </p>
            </div>

            <div class="static-column">
              <figure class="static-image size-large is-resized">
                <img
                  loading="lazy"
                  v-bind:src="staticSlide.images[0]"
                  alt=""
                  width="238"
                  height="177"
                />
              </figure>

              <figure class="static-image size-large is-resized">
                <img
                  loading="lazy"
                  v-bind:src="staticSlide.images[1]"
                  alt=""
                  srcset="
                    http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2020_04_kreis-1.png         450w,
                    http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2020_04_kreis-1-300x300.png 300w,
                    http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2020_04_kreis-1-150x150.png 150w
                  "
                  width="360"
                  height="360"
                  sizes="(max-width: 360px) 100vw, 360px"
                />
              </figure>
            </div>
          </div>

          <div class="static-image">
            <figure id="messageImage" class="aligncenter size-large is-resized">
              <img
                loading="lazy"
                v-bind:src="staticSlide.images[2]"
                alt=""
                srcset="
                  http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2020_11_Tannenbaum-1.png         482w,
                  http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2020_11_Tannenbaum-1-300x241.png 300w
                "
                width="162"
                height="130"
                sizes="(max-width: 162px) 100vw, 162px"
              />
            </figure>
          </div>

          <div class="message">
            <p class="has-text-align-center">
              <strong>Adventsverkauf:&nbsp;</strong>Sonntag den 22.11.2020 von
              10-17 Uhr
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Liebe",
  props: ["staticSlide"],
};
</script>

<style scoped>
figure {
  margin: 0 0 1rem;
}

.workTime {
  padding: 0px 0px 0px 40px;
  margin: 16px 0px;
}

b,strong {
  font-weight: bolder;
}

p {
  margin-top: 0;
  margin-bottom: 1rem;
}

li {
  font-size: 15px;
  list-style-type: disc;
  line-height: 1.75;
}

.static-container.section h1,
.static-container.section h2,
.static-container.section h3,
.static-container.section h4,
.static-container.section h5,
.static-container.section h6 {
  margin-bottom: 30px;
}

.has-text-align-center {
  text-align: center;
}

.static-container.section strong {
  color: black;
}

h1 {
  font-size: 2.5rem;
}

h2 {
    color: #212529;
}

h3 {
  font-size: 1.75rem;
}

.h2,h2 {
  font-size: 2rem;
}

.h1,.h2,.h3,.h4,.h5,.h6,h1,h2,h3,h4,h5,h6 {
  margin-bottom: 0.5rem;
  font-weight: 500;
  line-height: 1.2;
}

h1,h2,h3,h4,h5,h6 {
  margin-top: 0;
  margin-bottom: 0.5rem;
}
</style>
