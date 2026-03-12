# Tra Rete e Realtà — Blog su Social Media e Tecnologia

**Autore:** Lazar Cristian  
**Progetto scolastico** — Anno 2025/2026  
**Sito live:** [lazar-cristian.github.io/Blog_social](https://lazar-cristian.github.io/Blog_social/)

---

## Indice

1. [Menu di Navigazione](#1-menu-di-navigazione)
2. [Hero Banner Homepage](#2-hero-banner-homepage)
3. [Articolo in Evidenza](#3-articolo-in-evidenza)
4. [Griglia Altri Articoli](#4-griglia-altri-articoli)
5. [Pagina Articoli — Lista Anteprime](#5-pagina-articoli--lista-anteprime)
6. [Articolo Singolo Completo](#6-articolo-singolo-completo)
7. [Sezione Commenti](#7-sezione-commenti)
8. [Pagina Chi Siamo](#8-pagina-chi-siamo)
9. [Pagina Contatti](#9-pagina-contatti)
10. [Footer](#10-footer)
11. [Responsive Mobile](#11-responsive-mobile)
12. [Palette Colori e Tipografia](#12-palette-colori-e-tipografia)
13. [Struttura File](#13-struttura-file)

---

## 1. Menu di Navigazione

### Requisito Funzionale

Il sito deve contenere un **menu di navigazione principale** posizionato nella parte superiore della pagina e visibile in tutte le pagine del blog. Il menu deve permettere all'utente di spostarsi facilmente tra le sezioni del sito.

Il menu deve contenere le seguenti voci:
- **Home**
- **Articoli**
- **Chi siamo**
- **Contatti**

Ogni voce deve essere cliccabile e portare alla rispettiva pagina. La voce attiva (pagina corrente) deve essere evidenziata tramite la classe `active`. Il menu deve rimanere visibile durante lo scroll della pagina (`position: sticky`).

### Codice HTML

```html
<header>
    <div class="container">
        <a href="index.html" class="logo">Tra Rete e Realtà</a>
        <nav>
            <ul>
                <li><a href="index.html" class="active">Home</a></li>
                <li><a href="articoli.html">Articoli</a></li>
                <li><a href="chisiamo.html">Chi siamo</a></li>
                <li><a href="contatti.html">Contatti</a></li>
            </ul>
        </nav>
    </div>
</header>
```

### Requisito Grafico

Il menu deve avere uno stile **moderno**, coerente con la palette del blog.

**Caratteristiche grafiche:**
- **Sfondo:** Bianco semi-trasparente con effetto vetro (`backdrop-filter: blur(20px)`)
- **Altezza fissa:** 48px con contenuto centrato verticalmente
- **Logo:** 28px, grassetto, colore `#1d1d1f`, si ingrandisce leggermente al hover (`scale(1.03)`)
- **Voci di menu:** 12px, `opacity: 0.8` a riposo, `opacity: 1` al hover e sulla voce attiva
- **Bordo inferiore:** sottile linea `1px solid rgba(0,0,0,0.1)`
- **Comportamento:** `position: sticky`, rimane visibile sopra a tutto (`z-index: 1000`)

---

## 2. Hero Banner Homepage

### Requisito Funzionale

La homepage deve includere un **hero banner** di grande impatto visivo, posizionato subito sotto il menu. Deve presentare il blog all'utente con un titolo principale, un testo descrittivo e un pulsante di chiamata all'azione (CTA).

Il banner deve contenere:
- Titolo principale `h2` del blog
- Sottotitolo descrittivo della missione del blog
- Immagine di sfondo fotografica con overlay scuro
- Pulsante CTA "Esplora gli articoli" che porta a `articoli.html`
- Effetto parallax allo scroll tramite JavaScript

### Codice HTML

```html
<section class="hero" id="hero">
    <div class="container">
        <div class="hero-content">
            <h2>Scopri il confine tra mondo digitale e vita reale</h2>
            <p>Un blog dedicato alla consapevolezza nell'uso dei social media
               e alla riflessione sul nostro rapporto con la tecnologia.</p>
            <a href="articoli.html" class="cta-button">Esplora gli articoli</a>
        </div>
    </div>
</section>
```

### Requisito Grafico

Il hero banner deve essere visivamente **impattante** e trasmettere il tema del blog al primo sguardo.

**Caratteristiche grafiche:**
- **Altezza minima:** 650px con padding verticale 120px
- **Sfondo:** Fotografia da Unsplash con overlay gradiente diagonale scuro `rgba(15,23,42,0.75)`
- **Titolo `h2`:** 64px, bianco puro, `font-weight: 700`, doppio `text-shadow` per leggibilità
- **Sottotitolo `p`:** 28px, bianco al 98%
- **Pulsante CTA:** forma a pillola (`border-radius: 980px`), sfondo bianco, testo blu `#1e40af`
- **Hover pulsante:** si solleva con `translateY(-2px) scale(1.05)` e ombra più intensa

---

## 3. Articolo in Evidenza

### Requisito Funzionale

La homepage deve includere una sezione dedicata all'**articolo principale del blog**, visualizzato in una card grande e cliccabile. Tutta la card è un link che porta all'articolo completo. All'hover la card si solleva e l'immagine fa un leggero zoom.

La card deve contenere:
- Immagine di copertina a tutta larghezza
- Titolo dell'articolo
- Estratto del contenuto
- Link "Leggi l'articolo" con freccia animata

### Codice HTML

```html
<section class="featured-article">
    <div class="container">
        <h3 class="section-title">In evidenza</h3>
        <a href="articolo-paradosso.html" class="main-article">
            <img src="[url-immagine]" alt="Il paradosso della connessione sui social media">
            <div class="article-content">
                <h4>Il paradosso della connessione: più social, meno sociali?</h4>
                <p>Esploriamo come i social media abbiano trasformato le nostre relazioni,
                   creando una rete globale di connessioni virtuali ma spesso impoverendone
                   la profondità nella vita reale.</p>
                <span class="read-more">Leggi l'articolo</span>
            </div>
        </a>
    </div>
</section>
```

### Requisito Grafico

La card in evidenza deve essere il **punto focale** della homepage, grande e ben visibile.

**Caratteristiche grafiche:**
- **Sfondo sezione:** Bianco `#fff`, padding `100px 0`
- **Card:** `border-radius: 28px`, bordo `1px solid #d2d2d7`, ombra `0 6px 30px rgba(0,0,0,0.08)`
- **Immagine copertina:** altezza 420px, `object-fit: cover`
- **Titolo `h4`:** 40px, `font-weight: 600`, centrato, colore `#1d1d1f`
- **Estratto `p`:** 21px, grigio `#6e6e73`, centrato
- **Hover card:** bordo diventa blu `#0071e3`, `translateY(-8px)`, zoom immagine `scale(1.03)`
- **Link "Leggi l'articolo":** blu `#0071e3`, freccia `›` che si sposta a destra al hover

---

## 4. Griglia Altri Articoli

### Requisito Funzionale

La homepage deve mostrare gli altri articoli del blog in una **griglia a 2 colonne**, ciascuno visualizzato come card cliccabile. Ogni card porta all'articolo completo.

Ogni card deve mostrare:
- Immagine di copertina
- Titolo dell'articolo
- Estratto del contenuto
- Link "Leggi l'articolo"

### Codice HTML

```html
<section class="other-articles">
    <div class="container">
        <h3 class="section-title">Altri articoli</h3>
        <div class="articles-grid">

            <div class="article-card">
                <a href="articolo-algoritmi.html">
                    <img src="[url-immagine]" alt="Algoritmi e codice su schermo">
                    <div class="card-content">
                        <h4>Gli algoritmi che modellano la nostra realtà</h4>
                        <p>Un'analisi su come gli algoritmi dei social media influenzano
                           ciò che vediamo e pensiamo ogni giorno.</p>
                        <span class="read-more">Leggi l'articolo</span>
                    </div>
                </a>
            </div>

            <div class="article-card">
                <a href="articolo-detox.html">
                    <img src="[url-immagine]" alt="Digital detox - segnale no smartphone">
                    <div class="card-content">
                        <h4>Digital detox: riconnettersi con sé stessi</h4>
                        <p>Consigli pratici per prendersi una pausa dalla tecnologia
                           e riscoprire il valore del tempo offline.</p>
                        <span class="read-more">Leggi l'articolo</span>
                    </div>
                </a>
            </div>

        </div>
    </div>
</section>
```

### Requisito Grafico

Le card della griglia devono essere **coerenti** con la card in evidenza ma più compatte.

**Caratteristiche grafiche:**
- **Sfondo sezione:** Grigio chiarissimo `#f5f5f7`, padding `100px 0` — alternanza visiva con la sezione bianca
- **Griglia:** `display: grid`, `grid-template-columns: repeat(2, 1fr)`, `gap: 24px`
- **Immagine copertina:** altezza 280px, `object-fit: cover`
- **Titolo `h4`:** 28px, `font-weight: 600`, centrato
- **Estratto `p`:** 17px, grigio `#6e6e73`, centrato
- **Hover:** identico alla card in evidenza (bordo blu, elevazione, zoom immagine)

---

## 5. Pagina Articoli — Lista Anteprime

### Requisito Funzionale

La pagina `articoli.html` deve mostrare **tutti gli articoli del blog** in una lista verticale di card. Ogni card è cliccabile e porta all'articolo completo. Un titolo e un sottotitolo introducono la pagina.

Ogni card deve contenere:
- Immagine di copertina
- Data di pubblicazione
- Titolo dell'articolo
- Estratto del contenuto

### Codice HTML

```html
<main class="articles-page">
    <div class="container">
        <h2 class="page-title">Articoli</h2>
        <p class="page-intro">Esplora tutti gli articoli del blog su social media e tecnologia.</p>

        <a href="articolo-paradosso.html" class="article-preview">
            <img src="[url-immagine]" alt="Il paradosso della connessione">
            <div class="article-meta">
                <span class="date">15 Febbraio 2026</span>
            </div>
            <h3>Il paradosso della connessione: più social, meno sociali?</h3>
            <p>Esploriamo come i social media abbiano trasformato le nostre relazioni,
               creando una rete globale di connessioni virtuali ma spesso impoverendone
               la profondità nella vita reale.</p>
        </a>

        <!-- altre card .article-preview -->
    </div>
</main>
```

### Requisito Grafico

Le card devono essere chiare, ordinate e invitare alla lettura.

**Caratteristiche grafiche:**
- **Titolo pagina `h2`:** 56px, centrato, colore `#1d1d1f`
- **Sottotitolo:** 21px, grigio `#6e6e73`, centrato, `max-width: 640px`
- **Card anteprima:** `border-radius: 28px`, immagine altezza 360px
- **Data:** 14px, grigio chiaro `#86868b`, centrata
- **Titolo articolo `h3`:** 32px, `font-weight: 600`, centrato
- **Estratto `p`:** 19px, grigio `#6e6e73`, centrato
- **Hover:** bordo blu `#0071e3`, `translateY(-8px)`, zoom immagine

---

## 6. Articolo Singolo Completo

### Requisito Funzionale

Ogni articolo deve avere una **pagina dedicata** con il contenuto completo. In cima alla pagina deve esserci un link "← Torna agli Articoli". In fondo alla pagina un pulsante di ritorno e la sezione commenti.

La pagina deve contenere:
- Link "← Torna agli Articoli" nella parte alta
- Immagine di copertina a larghezza piena
- Data di pubblicazione
- Titolo `h3` centrato
- Corpo dell'articolo con almeno 5 paragrafi
- Sezione commenti (Requisito 7)
- Pulsante "Torna agli articoli" in fondo

### Codice HTML

```html
<main class="articles-page">
    <div class="container">

        <a href="articoli.html" class="article-back-link">← Torna agli Articoli</a>

        <article class="full-article">
            <img src="[url-immagine]" alt="Il paradosso della connessione">
            <div class="article-meta">
                <span class="date">15 Febbraio 2026</span>
            </div>
            <h3>Il paradosso della connessione: più social, meno sociali?</h3>
            <div class="article-body">
                <p>Viviamo nell'era della connessione perpetua. I nostri smartphone
                   ci tengono legati a centinaia, a volte migliaia di persone attraverso
                   piattaforme come Instagram, Facebook, TikTok e Twitter.</p>
                <p>Il paradosso della connessione digitale risiede proprio in questa
                   contraddizione: mentre i social media ci promettono di avvicinarci
                   agli altri, spesso finiscono per allontanarci dalle persone
                   fisicamente presenti nella nostra vita.</p>
                <!-- altri paragrafi -->
            </div>
        </article>

        <!-- Sezione commenti -->

        <div style="text-align: center; margin-top: 48px;">
            <a href="articoli.html" class="cta-button">Torna agli articoli</a>
        </div>

    </div>
</main>
```

### Requisito Grafico

La pagina articolo deve essere **leggibile e confortevole**, con ampi margini laterali.

**Caratteristiche grafiche:**
- **Link di ritorno:** 15px, blu `#0071e3`, sottolineatura al hover
- **Immagine copertina:** altezza 480px, `object-fit: cover`, a tutta larghezza della card
- **Data:** 14px, grigio `#86868b`, centrata, `padding: 32px 56px 0`
- **Titolo `h3`:** 48px, `font-weight: 600`, centrato, `padding: 16px 56px`
- **Corpo testo `p`:** 21px, `line-height: 1.5`, colore `#1d1d1f`, `padding: 32px 56px 56px`
- **Pulsante finale:** riusa lo stile `.cta-button` della hero (pillola bianca/blu)

---

## 7. Sezione Commenti

### Requisito Funzionale

Sotto ogni articolo deve essere presente una **sezione commenti** che mostra i commenti degli utenti e permette di aggiungerne di nuovi tramite un form.

La sezione deve contenere:
- Titolo "Commenti" e testo introduttivo
- Commenti esistenti con avatar emoji, nome autore, data e testo
- Form per nuovo commento con campi: Nome, Email (affiancati), testo messaggio
- Pulsante "Invia commento"

### Codice HTML

```html
<section class="comments-section">
    <h3>Commenti</h3>
    <p class="comments-intro">Condividi il tuo punto di vista sull'argomento.</p>

    <div class="comment">
        <div class="avatar">
            <div class="avatar-default">💬</div>
        </div>
        <div class="comment-content">
            <div class="comment-meta">
                <span class="comment-author">Giorgio</span>
                <span class="comment-date">20 febbraio 2026</span>
            </div>
            <div class="comment-text">
                <p>Questo articolo mi ha fatto riflettere su quante cene ho passato
                   guardando lo schermo invece delle persone accanto a me...</p>
            </div>
        </div>
    </div>

    <form class="comment-form">
        <h4>Lascia un commento</h4>
        <div class="form-row">
            <input type="text" placeholder="Nome" required>
            <input type="email" placeholder="Email" required>
        </div>
        <textarea placeholder="Scrivi il tuo commento..." rows="4" required></textarea>
        <button type="submit" class="submit-button">Invia commento</button>
    </form>
</section>
```

### Requisito Grafico

La sezione commenti deve essere **visivamente separata** dal corpo dell'articolo.

**Caratteristiche grafiche:**
- **Sfondo sezione:** `#fafafa`, `border-radius: 20px`, bordo grigio, `padding: 40px`
- **Avatar emoji:** cerchio 48px, sfondo azzurro `#e8f0fe`, emoji 22px centrata
- **Nome autore:** 15px, `font-weight: 600` | **Data:** 13px, grigio `#86868b`
- **Testo commento:** 16px, `line-height: 1.6`
- **Form nuovo commento:** card bianca interna, `border-radius: 14px`, `padding: 28px`
- **Campi Nome/Email:** affiancati in riga con `display: flex; gap: 16px`
- **Input focus:** bordo blu `#0071e3` + glow `rgba(0,113,227,0.1)`
- **Pulsante:** pillola blu `#0071e3`, larghezza 100%, `hover: scale(1.02)`

---

## 8. Pagina Chi Siamo

### Requisito Funzionale

La pagina `chisiamo.html` deve presentare il blog e la sua missione. Deve includere un'immagine circolare, un titolo, un sottotitolo e due sezioni di testo descrittive.

La pagina deve contenere:
- Titolo `h2` "Chi siamo" centrato
- Sottotitolo descrittivo centrato
- Immagine circolare del team
- Sezione "Il nostro progetto" con testo descrittivo
- Sezione "La nostra missione" con testo descrittivo

### Codice HTML

```html
<main class="about-page">
    <div class="container">
        <h2 class="page-title">Chi siamo</h2>
        <p class="page-intro">Siamo un gruppo di studenti appassionati
           di tecnologia e comunicazione digitale.</p>

        <div class="about-content">
            <div class="about-image">
                <img src="[url-immagine]" alt="Il team di Tra Rete e Realtà">
            </div>
            <div class="about-text">
                <h3>Il nostro progetto</h3>
                <p>Tra Rete e Realtà è nato come progetto scolastico con l'obiettivo
                   di analizzare l'impatto dei social media sulla società contemporanea.
                   Vogliamo offrire spunti di riflessione su un tema che ci riguarda
                   tutti ogni giorno.</p>

                <h3>La nostra missione</h3>
                <p>Crediamo che la tecnologia debba essere uno strumento di crescita
                   personale e collettiva. Per questo promuoviamo un uso consapevole
                   e critico dei social media, senza demonizzarli ma imparando a
                   conoscerli meglio.</p>
            </div>
        </div>
    </div>
</main>
```

### Requisito Grafico

La pagina deve essere **pulita e personale**, centrata sulla presentazione del team.

**Caratteristiche grafiche:**
- **Sfondo:** Bianco `#fff`, padding `80px 0`
- **Titolo `h2`:** 56px, centrato, `font-weight: 600`
- **Sottotitolo:** 21px, grigio `#6e6e73`, centrato, `max-width: 640px`
- **Immagine:** cerchio 240×240px (`border-radius: 50%`), centrata, bordo grigio e ombra leggera
- **Titoli sezione `h3`:** 32px, `font-weight: 600`, `margin-top: 40px` (eccetto il primo)
- **Testo:** 21px, `line-height: 1.5`, colore `#1d1d1f`

---

## 9. Pagina Contatti

### Requisito Funzionale

La pagina `contatti.html` deve permettere agli utenti di contattare il team. Deve avere un layout a **2 colonne**: a sinistra le informazioni di contatto, a destra un form.

La pagina deve contenere:
- Titolo `h2` e sottotitolo allineati a sinistra
- Colonna sinistra: icone circolari con email e numero di telefono
- Colonna destra: form con campi Nome, Cognome, Email, Messaggio
- Pulsante "Invia messaggio" visibile e cliccabile

### Codice HTML

```html
<main class="contact-page">
    <div class="container">
        <h2 class="page-title">Contatti</h2>
        <p class="page-intro">Hai domande o vuoi collaborare? Scrivici!</p>

        <div class="contact-wrapper">
            <div class="contact-left">
                <div class="contact-method">
                    <div class="icon">📧</div>
                    <div>
                        <h4>Email</h4>
                        <p>traereterealta@gmail.com</p>
                    </div>
                </div>
                <div class="contact-method">
                    <div class="icon">📞</div>
                    <div>
                        <h4>Telefono</h4>
                        <p>+39 011 000 0000</p>
                    </div>
                </div>
            </div>

            <div class="contact-right">
                <form class="contact-form-inline">
                    <div class="form-group">
                        <label>Nome</label>
                        <input type="text" placeholder="Il tuo nome">
                    </div>
                    <div class="form-group">
                        <label>Cognome</label>
                        <input type="text" placeholder="Il tuo cognome">
                    </div>
                    <div class="form-group">
                        <label>Email</label>
                        <input type="email" placeholder="La tua email">
                    </div>
                    <div class="form-group">
                        <label>Messaggio</label>
                        <textarea placeholder="Scrivi il tuo messaggio..." rows="5"></textarea>
                    </div>
                    <button type="submit" class="submit-button">Invia messaggio</button>
                </form>
            </div>
        </div>
    </div>
</main>
```

### Requisito Grafico

La pagina contatti deve avere un aspetto **professionale** con layout chiaro a due colonne.

**Caratteristiche grafiche:**
- **Sfondo:** Grigio chiaro `#f5f5f7` — titolo e sottotitolo allineati a sinistra
- **Layout:** `display: flex`, `gap: 56px` — colonna sinistra larghezza fissa 320px
- **Icone contatto:** cerchi 46px, sfondo blu `#0071e3`, `box-shadow` colorata
- **Card form destra:** sfondo bianco, `border-radius: 20px`, `padding: 40px 44px`
- **Input:** `border-radius: 10px`, `padding: 13px` — focus con bordo blu e glow
- **Textarea:** `min-height: 160px`, ridimensionabile solo in verticale
- **Pulsante:** pillola blu `#0071e3`, larghezza 100%, 17px

---

## 10. Footer

### Requisito Funzionale

Tutte le pagine devono avere un **footer identico** diviso in 3 colonne: Link Utili, Seguici e Newsletter. In fondo c'è la riga del copyright.

Il footer deve contenere:
- **Colonna 1:** link rapidi Home, Articoli, Chi Siamo, Contatti
- **Colonna 2:** link ai social (Twitter, Facebook, Instagram)
- **Colonna 3:** form newsletter con input email e pulsante "Iscriviti"
- Riga copyright: © 2026 Tra Rete e Realtà

### Codice HTML

```html
<footer>
    <div class="container">
        <div class="footer-grid">

            <div class="footer-col">
                <h5>Link utili</h5>
                <ul>
                    <li><a href="index.html">Home</a></li>
                    <li><a href="articoli.html">Articoli</a></li>
                    <li><a href="chisiamo.html">Chi siamo</a></li>
                    <li><a href="contatti.html">Contatti</a></li>
                </ul>
            </div>

            <div class="footer-col">
                <h5>Seguici</h5>
                <div class="footer-social">
                    <a href="#">Twitter</a>
                    <a href="#">Facebook</a>
                    <a href="#">Instagram</a>
                </div>
            </div>

            <div class="footer-col">
                <h5>Newsletter</h5>
                <p>Iscriviti alla nostra newsletter per le ultime novità!</p>
                <form class="newsletter-form">
                    <input type="email" placeholder="Indirizzo email">
                    <button type="submit">Iscriviti</button>
                </form>
            </div>

        </div>
        <div class="footer-bottom">
            <p>&copy; 2026 Tra Rete e Realtà. Tutti i diritti riservati.</p>
        </div>
    </div>
</footer>
```

### Requisito Grafico

Il footer deve avere un aspetto **scuro e professionale**, in contrasto con il resto del sito.

**Caratteristiche grafiche:**
- **Sfondo:** Blu scuro/grafite `#1f2937`, testo bianco, `padding-top: 56px`
- **Griglia 3 colonne:** `grid-template-columns: 1fr 1fr 1.6fr`, `gap: 48px`
- **Intestazioni `h5`:** 11px, tutto maiuscolo, `letter-spacing: 0.1em`, `opacity: 0.7`
- **Link:** bianco al 75% a riposo, bianco pieno al hover
- **Form newsletter:** input con sfondo glass `rgba(255,255,255,0.08)` + pulsante blu `#0071e3` affiancati
- **Riga copyright:** separatore bianco trasparente, testo 12px bianco al 40%
- **Mobile:** le 3 colonne si impilano in una sola, form newsletter in colonna verticale

---

## 11. Responsive Mobile

### Requisito Funzionale

Il sito deve adattarsi automaticamente agli schermi con larghezza **≤768px** tramite una media query CSS. Tutti gli elementi devono ridimensionarsi per garantire leggibilità e usabilità su smartphone.

Adattamenti principali richiesti:
- Menu: voci più piccole, logo ridotto
- Hero: titolo e testo ridimensionati, altezza minima ridotta
- Griglia articoli: da 2 colonne a **1 colonna**
- Layout contatti: da 2 colonne affiancate a **1 colonna** sovrapposta
- Form commenti: campi Nome/Email da riga a **colonna verticale**
- Footer: 3 colonne diventano **1 colonna**

### Codice CSS

```css
@media (max-width: 768px) {

    header .logo { font-size: 22px; }
    header nav ul { gap: 16px; }
    header nav a { font-size: 11px; }

    .hero { min-height: 500px; padding: 80px 0; }
    .hero-content h2 { font-size: 40px; }
    .hero-content p  { font-size: 21px; }

    .main-article img { height: 280px; }
    .main-article h4  { font-size: 28px; }

    .articles-grid { grid-template-columns: 1fr; }
    .article-card img { height: 220px; }

    .page-title { font-size: 40px; }

    .full-article img { height: 280px; }
    .full-article h3  { font-size: 32px; padding: 12px 24px; }
    .full-article .article-body { padding: 20px 24px 36px; }
    .full-article .article-body p { font-size: 17px; }

    .contact-wrapper { flex-direction: column; }
    .contact-left { width: 100%; }

    .comment-form .form-row { flex-direction: column; }

    .footer-grid { grid-template-columns: 1fr; gap: 32px; }
    .newsletter-form { flex-direction: column; }
    .newsletter-form input,
    .newsletter-form button { width: 100%; }

}
```

### Requisito Grafico

**Caratteristiche grafiche su mobile:**
- **Punto di rottura unico:** `max-width: 768px`
- **Hero:** altezza minima scende a 500px, titolo da 64px → 40px
- **Griglia:** da `repeat(2,1fr)` → `grid-template-columns: 1fr`
- **Contatti:** `flex-direction: column`, entrambe le colonne a larghezza 100%
- **Footer:** `grid-template-columns: 1fr`, form newsletter in colonna
- Tutti i font e padding si riducono proporzionalmente per leggibilità ottimale

---

## 12. Palette Colori e Tipografia

### Colori

| Colore | Hex | Utilizzo |
|---|---|---|
| Quasi nero | `#1d1d1f` | Testo principale, titoli |
| Blu Apple | `#0071e3` | Link, pulsanti, bordi hover, icone |
| Blu intenso | `#1e40af` | Testo del pulsante CTA hero |
| Bianco puro | `#ffffff` | Sfondi, testo su scuro |
| Grigio chiaro | `#f5f5f7` | Sfondo sezione "Altri articoli", pagina Contatti |
| Grigio card | `#fafafa` | Sfondo sezione commenti |
| Grigio bordi | `#d2d2d7` | Bordi di card e input |
| Grigio testo | `#6e6e73` | Estratti, descrizioni secondarie |
| Grigio metadati | `#86868b` | Date, informazioni secondarie |
| Grafite footer | `#1f2937` | Sfondo footer |
| Azzurro avatar | `#e8f0fe` | Sfondo avatar emoji commenti |

### Tipografia

Il sito usa il **font di sistema** per garantire velocità e coerenza:

```css
font-family: -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'Segoe UI', Arial, sans-serif;
```

| Elemento | Dimensione | Peso |
|---|---|---|
| Titolo hero `h2` | 64px | 700 |
| Titolo pagine `h2` | 56px | 600 |
| Titolo articolo singolo `h3` | 48px | 600 |
| Titolo in evidenza `h4` | 40px | 600 |
| Titolo sezione | 32px | 600 |
| Corpo articolo `p` | 21px | 400 |
| Logo | 28px | 700 |
| Menu navigazione | 12px | 400 |
| Copyright footer | 12px | 400 |

---

## 13. Struttura File

```
Blog_social/
├── index.html              ← Homepage (hero, articolo in evidenza, altri articoli)
├── articoli.html           ← Lista di tutti gli articoli
├── articolo-paradosso.html ← Articolo: "Il paradosso della connessione"
├── articolo-algoritmi.html ← Articolo: "Gli algoritmi che modellano la nostra realtà"
├── articolo-detox.html     ← Articolo: "Digital detox: riconnettersi con sé stessi"
├── chisiamo.html           ← Pagina Chi siamo
├── contatti.html           ← Pagina Contatti con form
├── style.css               ← Foglio di stile unico per tutte le pagine
├── immagini/               ← Cartella immagini locali
└── .nojekyll               ← File per GitHub Pages (disabilita Jekyll)
```

---

*Progetto realizzato per l'anno scolastico 2025/2026 — Tra Rete e Realtà*
