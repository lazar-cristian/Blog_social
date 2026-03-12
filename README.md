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
Il menu rimane visibile in cima alla pagina durante lo scroll (posizione `sticky`). Contiene il logo cliccabile del blog e 4 voci di navigazione: **Home**, **Articoli**, **Chi siamo**, **Contatti**. La voce della pagina corrente viene evidenziata tramite la classe `active`.

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
- Sfondo bianco semi-trasparente con effetto **glass morphism** (`backdrop-filter: blur(20px)`)
- Altezza fissa: **48px**
- Logo: `28px`, grassetto, colore `#1d1d1f`, si ingrandisce al 103% all'hover
- Voci di menu: `12px`, `opacity: 0.8` a riposo, `opacity: 1` al hover/active
- Bordo inferiore sottile: `1px solid rgba(0,0,0,0.1)`
- `z-index: 1000` — si sovrappone a tutto durante lo scroll

### Codice CSS
```css
header {
    background: rgba(255, 255, 255, 0.8);
    backdrop-filter: saturate(180%) blur(20px);
    -webkit-backdrop-filter: saturate(180%) blur(20px);
    position: sticky;
    top: 0;
    z-index: 1000;
    border-bottom: 1px solid rgba(0, 0, 0, 0.1);
}

header .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 48px;
    max-width: 100%;
    padding: 0 32px;
}

header .logo {
    font-size: 28px;
    font-weight: 700;
    color: #1d1d1f;
    letter-spacing: -0.02em;
    transition: transform 0.3s ease;
}

header .logo:hover { transform: scale(1.03); }

header nav ul {
    list-style: none;
    display: flex;
    gap: 32px;
}

header nav a {
    font-size: 12px;
    color: #1d1d1f;
    opacity: 0.8;
    transition: opacity 0.3s ease;
}

header nav a:hover,
header nav a.active { opacity: 1; }
```

### Immagine Esemplificativa
```
┌─────────────────────────────────────────────────────────────────┐
│  Tra Rete e Realtà          Home  Articoli  Chi siamo  Contatti │
└─────────────────────────────────────────────────────────────────┘
  [logo 28px grassetto]        [voci 12px, gap 32px tra ognuna]
```

---

## 2. Hero Banner Homepage

### Requisito Funzionale
Sezione banner grande con immagine di sfondo fotografica e testo sovrapposto. Contiene un titolo principale, un testo descrittivo e un pulsante CTA (Call To Action) che porta alla pagina Articoli. Implementa un effetto **parallax** allo scroll tramite JavaScript.

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
- Altezza minima: **650px**, padding verticale `120px`
- Immagine di sfondo da Unsplash con overlay gradiente scuro (`rgba(15,23,42,0.75)`)
- Vignettatura radiale ai bordi tramite `::after`
- Titolo `h2`: `64px`, bianco, grassetto, `text-shadow` doppia per leggibilità
- Testo descrittivo: `28px`, bianco al 98%
- Pulsante CTA: sfondo bianco, testo blu `#1e40af`, forma a pillola (`border-radius: 980px`), si solleva all'hover con `translateY(-2px) scale(1.05)`

### Codice CSS
```css
.hero {
    min-height: 650px;
    padding: 120px 0;
    text-align: center;
    position: relative;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
}

.hero::before {
    content: '';
    position: absolute;
    top: -40%; left: -10%; right: -10%; bottom: -40%;
    background:
        linear-gradient(135deg, rgba(15,23,42,0.75) 0%, rgba(30,41,59,0.65) 50%, rgba(15,23,42,0.75) 100%),
        url('https://images.unsplash.com/photo-1639322537228-f710d846310a?w=1600&q=80') center/cover no-repeat;
    z-index: -2;
    will-change: transform;
}

.hero-content h2 {
    font-size: 64px;
    font-weight: 700;
    color: #ffffff;
    text-shadow: 0 4px 20px rgba(0,0,0,0.5), 0 2px 8px rgba(0,0,0,0.3);
    margin-bottom: 20px;
}

.hero-content p {
    font-size: 28px;
    color: rgba(255,255,255,0.98);
    margin-bottom: 32px;
}

.cta-button {
    display: inline-block;
    background: rgba(255,255,255,0.98);
    color: #1e40af;
    padding: 14px 28px;
    border-radius: 980px;
    font-size: 17px;
    font-weight: 600;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    box-shadow: 0 4px 24px rgba(0,0,0,0.25);
}

.cta-button:hover {
    transform: scale(1.05) translateY(-2px);
    box-shadow: 0 6px 32px rgba(0,0,0,0.3);
}
```

### Immagine Esemplificativa
```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│         [Foto sfondo scurita con overlay gradiente]            │
│                                                                 │
│      Scopri il confine tra mondo digitale e vita reale         │
│            [titolo 64px bianco con text-shadow]                │
│                                                                 │
│    Un blog dedicato alla consapevolezza nell'uso dei social    │
│                    [testo 28px bianco]                          │
│                                                                 │
│                  [ Esplora gli articoli ]                       │
│               [pulsante pillola bianco/blu]                    │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 3. Articolo in Evidenza

### Requisito Funzionale
Sezione della homepage che mostra l'articolo principale del blog in una card grande e cliccabile. Tutta la card è un link che porta all'articolo completo. All'hover la card si solleva e l'immagine fa un leggero zoom.

### Codice HTML
```html
<section class="featured-article">
    <div class="container">
        <h3 class="section-title">In evidenza</h3>
        <a href="articolo-paradosso.html" class="main-article">
            <img src="[url-immagine]" alt="Immagine articolo in evidenza sui social media">
            <div class="article-content">
                <h4>Il paradosso della connessione: più social, meno sociali?</h4>
                <p>Esploriamo come i social media abbiano trasformato le nostre relazioni,
                   creando una rete globale di connessioni virtuali...</p>
                <span class="read-more">Leggi l'articolo</span>
            </div>
        </a>
    </div>
</section>
```

### Requisito Grafico
- Sfondo sezione: **bianco** `#fff`, padding `100px 0`
- Titolo sezione: `32px`, centrato, `margin-bottom: 60px`
- Card: `border-radius: 28px`, bordo `1px solid #d2d2d7`, `box-shadow: 0 6px 30px rgba(0,0,0,0.08)`
- Immagine copertina: altezza **420px**, `object-fit: cover`
- All'hover: bordo diventa blu `#0071e3`, ombra più intensa, `translateY(-8px)`, zoom immagine `scale(1.03)`
- Titolo `h4`: `40px`, semi-grassetto, centrato
- Estratto `p`: `21px`, grigio `#6e6e73`, centrato
- Link "Leggi l'articolo": blu `#0071e3`, con freccia `›` animata che si sposta a destra all'hover

### Codice CSS
```css
.main-article {
    display: flex;
    flex-direction: column;
    background-color: #fff;
    border-radius: 28px;
    overflow: hidden;
    border: 1px solid #d2d2d7;
    box-shadow: 0 6px 30px rgba(0,0,0,0.08);
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}

.main-article:hover {
    border-color: #0071e3;
    box-shadow: 0 12px 48px rgba(0,0,0,0.12);
    transform: translateY(-8px);
}

.main-article img {
    width: 100%;
    height: 420px;
    object-fit: cover;
    transition: transform 0.7s cubic-bezier(0.4, 0, 0.2, 1);
}

.main-article:hover img { transform: scale(1.03); }

.main-article .article-content {
    padding: 50px 56px 56px;
    text-align: center;
}

.main-article h4 { font-size: 40px; font-weight: 600; color: #1d1d1f; }
.main-article p  { font-size: 21px; color: #6e6e73; margin-bottom: 28px; }

.read-more {
    color: #0071e3;
    font-size: 17px;
    display: inline-flex;
    align-items: center;
    gap: 6px;
}

.read-more::after { content: '›'; font-size: 24px; transition: transform 0.3s ease; }
.read-more:hover::after { transform: translateX(4px); }
```

### Immagine Esemplificativa
```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│           [Immagine copertina — altezza 420px]                 │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│       Il paradosso della connessione: più social,              │
│                    meno sociali?                               │
│              [titolo 40px, centrato]                           │
│                                                                 │
│    Esploriamo come i social media abbiano trasformato...       │
│              [estratto 21px grigio, centrato]                  │
│                                                                 │
│                  Leggi l'articolo ›                            │
│                  [link blu animato]                            │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
   [hover: bordo blu, elevazione -8px, zoom immagine 1.03]
```

---

## 4. Griglia Altri Articoli

### Requisito Funzionale
Sezione della homepage con una griglia a 2 colonne che mostra le anteprime degli altri articoli del blog. Ogni card è completamente cliccabile e porta all'articolo corrispondente.

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
                    <img src="[url-immagine]" alt="Segnale di divieto smartphone in un bosco">
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
- Sfondo sezione: grigio chiarissimo `#f5f5f7`, padding `100px 0` — alternanza visiva con la sezione bianca
- Griglia: `display: grid`, `grid-template-columns: repeat(2, 1fr)`, `gap: 24px`
- Card: `border-radius: 28px`, stesso stile ombra della card in evidenza
- Immagine copertina: altezza **280px**, `object-fit: cover`
- Titolo `h4`: `28px`, semi-grassetto
- Descrizione `p`: `17px`, grigio `#6e6e73`
- All'hover: identico alla card in evidenza (bordo blu, elevazione, zoom immagine)

### Codice CSS
```css
.other-articles { background-color: #f5f5f7; padding: 100px 0; }

.articles-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 24px;
}

.article-card {
    background-color: #fff;
    border-radius: 28px;
    overflow: hidden;
    border: 1px solid #d2d2d7;
    box-shadow: 0 6px 30px rgba(0,0,0,0.08);
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}

.article-card:hover {
    border-color: #0071e3;
    box-shadow: 0 12px 48px rgba(0,0,0,0.12);
    transform: translateY(-8px);
}

.article-card img {
    width: 100%;
    height: 280px;
    object-fit: cover;
    transition: transform 0.7s cubic-bezier(0.4, 0, 0.2, 1);
}

.article-card:hover img { transform: scale(1.03); }

.article-card .card-content { padding: 40px 40px 48px; text-align: center; }
.article-card h4 { font-size: 28px; font-weight: 600; color: #1d1d1f; }
.article-card p  { font-size: 17px; color: #6e6e73; margin-bottom: 20px; }
```

### Immagine Esemplificativa
```
┌───────────────────────────┐  ┌───────────────────────────┐
│                           │  │                           │
│  [Immagine — 280px]       │  │  [Immagine — 280px]       │
│                           │  │                           │
├───────────────────────────┤  ├───────────────────────────┤
│  Gli algoritmi che        │  │  Digital detox:           │
│  modellano la nostra      │  │  riconnettersi con        │
│  realtà                   │  │  sé stessi                │
│  [28px semi-grassetto]    │  │  [28px semi-grassetto]    │
│                           │  │                           │
│  Un'analisi su come...    │  │  Consigli pratici per...  │
│  [17px grigio]            │  │  [17px grigio]            │
│                           │  │                           │
│  Leggi l'articolo ›       │  │  Leggi l'articolo ›       │
└───────────────────────────┘  └───────────────────────────┘
       [gap: 24px tra le due card — sfondo #f5f5f7]
```

---

## 5. Pagina Articoli — Lista Anteprime

### Requisito Funzionale
La pagina `articoli.html` mostra tutti gli articoli del blog in formato lista verticale. Ogni card anteprima ha immagine, data, titolo, estratto e link all'articolo completo. Un titolo e un sottotitolo introducono la pagina.

### Codice HTML
```html
<main class="articles-page">
    <div class="container">
        <h2 class="page-title">Articoli</h2>
        <p class="page-intro">Esplora tutti gli articoli del blog...</p>

        <div class="article-preview">
            <a href="articolo-paradosso.html">
                <img src="[url-immagine]" alt="...">
                <div class="article-meta">
                    <span class="date">15 Febbraio 2026</span>
                </div>
                <h3>Il paradosso della connessione: più social, meno sociali?</h3>
                <p>Esploriamo come i social media abbiano trasformato le nostre relazioni...</p>
            </a>
        </div>
        <!-- altre card .article-preview -->
    </div>
</main>
```

### Requisito Grafico
- Titolo pagina: `56px`, centrato, colore `#1d1d1f`
- Sottotitolo: `21px`, grigio `#6e6e73`, centrato, `max-width: 640px`
- Card anteprima: `border-radius: 28px`, immagine altezza **360px**
- Data: `14px`, grigio chiaro `#86868b`, centrata
- Titolo articolo: `32px`, semi-grassetto
- Estratto: `19px`, grigio `#6e6e73`
- Hover: bordo blu, `translateY(-8px)`, zoom immagine `scale(1.03)`

### Codice CSS
```css
.articles-page { padding: 80px 0; background-color: #fff; }

.page-title {
    font-size: 56px;
    font-weight: 600;
    color: #1d1d1f;
    text-align: center;
    margin-bottom: 12px;
}

.page-intro {
    font-size: 21px;
    color: #6e6e73;
    text-align: center;
    max-width: 640px;
    margin: 0 auto 80px;
}

.article-preview {
    border-radius: 28px;
    overflow: hidden;
    border: 1px solid #d2d2d7;
    box-shadow: 0 6px 30px rgba(0,0,0,0.08);
    margin-bottom: 32px;
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}

.article-preview:hover {
    border-color: #0071e3;
    transform: translateY(-8px);
}

.article-preview img { width: 100%; height: 360px; object-fit: cover; }
.article-preview .article-meta { padding: 32px 48px 0; color: #86868b; font-size: 14px; text-align: center; }
.article-preview h3 { font-size: 32px; font-weight: 600; text-align: center; padding: 12px 48px; }
.article-preview p  { font-size: 19px; color: #6e6e73; padding: 0 48px 48px; text-align: center; }
```

### Immagine Esemplificativa
```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│              [Immagine copertina — altezza 360px]              │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                    15 Febbraio 2026                            │
│                    [data 14px grigio]                          │
│                                                                 │
│        Il paradosso della connessione: più social,             │
│                     meno sociali?                              │
│                  [titolo 32px centrato]                        │
│                                                                 │
│     Esploriamo come i social media abbiano trasformato...      │
│              [estratto 19px grigio centrato]                   │
└─────────────────────────────────────────────────────────────────┘
```

---

## 6. Articolo Singolo Completo

### Requisito Funzionale
Ogni articolo ha una pagina dedicata (`articolo-*.html`) con: freccia di ritorno alla lista, immagine di copertina grande, data di pubblicazione, titolo e corpo dell'articolo suddiviso in paragrafi. In fondo alla pagina c'è un pulsante "Torna agli articoli".

### Codice HTML
```html
<main class="articles-page">
    <div class="container">
        <a href="articoli.html" class="article-back-link">← Torna agli Articoli</a>

        <article class="full-article">
            <img src="[url-immagine]" alt="...">
            <div class="article-meta">
                <span class="date">15 Febbraio 2026</span>
            </div>
            <h3>Il paradosso della connessione: più social, meno sociali?</h3>
            <div class="article-body">
                <p>Viviamo nell'era della connessione perpetua...</p>
                <p>Il paradosso della connessione digitale risiede proprio...</p>
                <!-- altri paragrafi -->
            </div>
        </article>

        <!-- Sezione commenti (vedi Requisito 7) -->

        <div style="text-align: center; margin-top: 48px;">
            <a href="articoli.html" class="cta-button">Torna agli articoli</a>
        </div>
    </div>
</main>
```

### Requisito Grafico
- Link di ritorno: `15px`, blu `#0071e3`, sottolineatura all'hover
- Card articolo: `border-radius: 28px`, `margin-bottom: 48px`
- Immagine copertina: altezza **480px**, `object-fit: cover`
- Data: `14px`, grigio chiaro `#86868b`, centrata
- Titolo `h3`: `48px`, semi-grassetto, centrato, `padding: 16px 56px`
- Corpo articolo `p`: `21px`, `line-height: 1.5`, `margin-bottom: 28px`, `padding: 32px 56px 56px`
- Pulsante di ritorno: riusa lo stile `.cta-button` della hero

### Codice CSS
```css
.article-back-link {
    display: inline-block;
    margin-bottom: 24px;
    font-size: 15px;
    color: #0071e3;
}

.article-back-link:hover { text-decoration: underline; }

.full-article {
    border-radius: 28px;
    overflow: hidden;
    border: 1px solid #d2d2d7;
    box-shadow: 0 6px 30px rgba(0,0,0,0.08);
    margin-bottom: 48px;
}

.full-article img { width: 100%; height: 480px; object-fit: cover; }

.full-article .article-meta {
    padding: 32px 56px 0;
    color: #86868b;
    font-size: 14px;
    text-align: center;
}

.full-article h3 {
    font-size: 48px;
    font-weight: 600;
    color: #1d1d1f;
    padding: 16px 56px;
    text-align: center;
}

.full-article .article-body { padding: 32px 56px 56px; }

.full-article .article-body p {
    font-size: 21px;
    line-height: 1.5;
    color: #1d1d1f;
    margin-bottom: 28px;
    letter-spacing: 0.011em;
}
```

### Immagine Esemplificativa
```
← Torna agli Articoli

┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│              [Immagine copertina — altezza 480px]              │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                    15 Febbraio 2026                            │
│                                                                 │
│        Il paradosso della connessione: più social,             │
│                     meno sociali?                              │
│                  [titolo 48px centrato]                        │
│                                                                 │
│  Viviamo nell'era della connessione perpetua. I nostri         │
│  smartphone ci tengono legati a centinaia...                   │
│  [corpo 21px, line-height 1.5, padding 56px laterale]         │
│                                                                 │
│  Il paradosso della connessione digitale risiede proprio...    │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘

              [ Torna agli articoli ]   ← pulsante pillola
```

---

## 7. Sezione Commenti

### Requisito Funzionale
Ogni articolo singolo ha una sezione commenti subito sotto la card dell'articolo. Mostra i commenti esistenti (con avatar emoji e nome autore) e un form per lasciare un nuovo commento con campi Nome, Email, testo e pulsante di invio.

### Codice HTML
```html
<section class="comments-section">
    <h3>Commenti</h3>
    <p class="comments-intro">Condividi il tuo punto di vista su connessione digitale e relazioni reali.</p>

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
- Sfondo sezione: `#fafafa`, `border-radius: 20px`, `padding: 40px`
- Titolo "Commenti": `24px`, semi-grassetto
- Ogni commento: `display: flex`, `gap: 16px`, separatore `border-bottom: 1px solid #e5e7eb`
- Avatar emoji: cerchio **48px**, sfondo azzurro `#e8f0fe`, emoji `22px`
- Nome autore: `15px`, semi-grassetto, colore scuro
- Data commento: `13px`, grigio `#86868b`
- Testo commento: `16px`, `line-height: 1.6`
- Form commento: card bianca interna, `border-radius: 14px`, `padding: 28px`
- Riga Nome/Email: `display: flex`, `gap: 16px` (su mobile si impilano in colonna)
- Pulsante "Invia commento": forma a pillola, sfondo blu `#0071e3`

### Codice CSS
```css
.comments-section {
    margin-top: 40px;
    padding: 40px;
    background-color: #fafafa;
    border-radius: 20px;
    border: 1px solid #d2d2d7;
}

.comment {
    display: flex;
    gap: 16px;
    margin-bottom: 32px;
    padding-bottom: 32px;
    border-bottom: 1px solid #e5e7eb;
}

.avatar-default {
    width: 48px; height: 48px;
    border-radius: 50%;
    background-color: #e8f0fe;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    flex-shrink: 0;
}

.comment-author { font-weight: 600; font-size: 15px; color: #1d1d1f; }
.comment-date   { font-size: 13px; color: #86868b; }
.comment-text p { font-size: 16px; line-height: 1.6; color: #1d1d1f; }

.comment-form {
    margin-top: 32px;
    padding: 28px;
    background-color: #fff;
    border-radius: 14px;
    border: 1px solid #d2d2d7;
}

.comment-form .form-row { display: flex; gap: 16px; margin-bottom: 16px; }
.comment-form .form-row input { flex: 1; padding: 12px 14px; border: 1px solid #d2d2d7; border-radius: 8px; }
.comment-form textarea { width: 100%; padding: 12px 14px; border: 1px solid #d2d2d7; border-radius: 8px; resize: vertical; margin-bottom: 16px; }

.comment-form .submit-button {
    width: 100%; padding: 12px;
    background: #0071e3; color: #fff;
    border: none; border-radius: 980px;
    font-size: 15px; cursor: pointer;
}
```

### Immagine Esemplificativa
```
┌─────────────────────────────────────────────────────────────────┐
│  Commenti                                                       │
│  Condividi il tuo punto di vista...                            │
│ ─────────────────────────────────────────────────────────────── │
│  [💬]  Giorgio           20 febbraio 2026                      │
│        Questo articolo mi ha fatto riflettere su quante        │
│        cene ho passato guardando lo schermo...                 │
│ ─────────────────────────────────────────────────────────────── │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │  Lascia un commento                                     │   │
│  │  [  Nome  ]  [  Email  ]                                │   │
│  │  [  Scrivi il tuo commento...                       ]   │   │
│  │  [  Scrivi il tuo commento...                       ]   │   │
│  │            [ Invia commento ]                           │   │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
```

---

## 8. Pagina Chi Siamo

### Requisito Funzionale
La pagina `chisiamo.html` presenta il blog e il team con un'immagine circolare di profilo, un titolo di pagina, un sottotitolo e due sezioni di testo: "Il nostro progetto" e "La nostra missione".

### Codice HTML
```html
<main class="about-page">
    <div class="container">
        <h2 class="page-title">Chi siamo</h2>
        <p class="page-intro">Siamo un gruppo di studenti appassionati di tecnologia...</p>

        <div class="about-content">
            <div class="about-image">
                <img src="[url-immagine]" alt="Il team di Tra Rete e Realtà">
            </div>
            <div class="about-text">
                <h3>Il nostro progetto</h3>
                <p>Tra Rete e Realtà è nato come progetto scolastico con l'obiettivo...</p>

                <h3>La nostra missione</h3>
                <p>Crediamo che la tecnologia debba essere uno strumento di crescita...</p>
            </div>
        </div>
    </div>
</main>
```

### Requisito Grafico
- Sfondo pagina: bianco `#fff`, padding `80px 0`
- Titolo `h2`: `56px`, centrato
- Sottotitolo: `21px`, grigio, centrato, `max-width: 640px`
- Layout contenuto: griglia colonna singola, `max-width: 800px`, centrata
- Immagine profilo: **240×240px**, `border-radius: 50%` (cerchio), centrata
- Titoli sezione `h3`: `32px`, semi-grassetto, `margin-top: 40px`
- Testo: `21px`, `line-height: 1.5`, colore `#1d1d1f`

### Codice CSS
```css
.about-page { padding: 80px 0; background-color: #fff; }

.about-content {
    display: grid;
    grid-template-columns: 1fr;
    gap: 48px;
    max-width: 800px;
    margin: 60px auto 0;
}

.about-image img {
    width: 240px; height: 240px;
    object-fit: cover;
    border-radius: 50%;
    margin: 0 auto;
    border: 1px solid #d2d2d7;
    box-shadow: 0 6px 30px rgba(0,0,0,0.08);
}

.about-text h3 {
    font-size: 32px;
    font-weight: 600;
    color: #1d1d1f;
    margin-bottom: 16px;
    margin-top: 40px;
}

.about-text h3:first-child { margin-top: 0; }

.about-text p {
    font-size: 21px;
    line-height: 1.5;
    color: #1d1d1f;
    margin-bottom: 24px;
}
```

### Immagine Esemplificativa
```
              Chi siamo
   [titolo 56px centrato]

   Siamo un gruppo di studenti appassionati di tecnologia...
   [sottotitolo 21px grigio centrato]

                  ( foto )
               [cerchio 240px]

   Il nostro progetto
   [h3 32px]
   Tra Rete e Realtà è nato come progetto scolastico...
   [testo 21px, line-height 1.5]

   La nostra missione
   [h3 32px]
   Crediamo che la tecnologia debba essere uno strumento...
```

---

## 9. Pagina Contatti

### Requisito Funzionale
La pagina `contatti.html` ha un layout a 2 colonne: a sinistra le informazioni di contatto (email e telefono con icone circolari colorate), a destra una card bianca con un form di contatto con campi Nome, Cognome, Email, Messaggio e pulsante di invio.

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
- Sfondo pagina: grigio chiaro `#f5f5f7`
- Titolo e sottotitolo: **allineati a sinistra** (override rispetto alle altre pagine)
- Layout a 2 colonne: `display: flex`, `gap: 56px`
- Colonna sinistra: larghezza fissa `320px` — icone circolari blu `#0071e3` da **46px**, con `box-shadow` colorata
- Colonna destra: `flex: 1` — card bianca con `border-radius: 20px`, `padding: 40px 44px`
- Campi del form: `border-radius: 10px`, focus con bordo blu e glow `rgba(0,113,227,0.1)`
- Textarea: `min-height: 160px`, ridimensionabile solo in verticale
- Pulsante: forma a pillola `border-radius: 980px`, sfondo blu `#0071e3`, larghezza 100%

### Codice CSS
```css
.contact-page { padding: 80px 0; background-color: #f5f5f7; }
.contact-page .page-title { text-align: left; }
.contact-page .page-intro { text-align: left; margin-left: 0; font-size: 17px; }

.contact-wrapper { display: flex; gap: 56px; align-items: flex-start; }

.contact-left { flex: 0 0 320px; display: flex; flex-direction: column; gap: 28px; }

.contact-method { display: flex; align-items: flex-start; gap: 16px; }

.contact-method .icon {
    width: 46px; height: 46px;
    border-radius: 50%;
    background-color: #0071e3;
    display: flex; align-items: center; justify-content: center;
    font-size: 20px;
    flex-shrink: 0;
    box-shadow: 0 4px 16px rgba(0,113,227,0.25);
}

.contact-right {
    flex: 1;
    background: #fff;
    border-radius: 20px;
    border: 1px solid #d2d2d7;
    box-shadow: 0 6px 30px rgba(0,0,0,0.08);
    padding: 40px 44px;
}

.form-group { margin-bottom: 18px; }
.form-group label { display: block; font-size: 15px; font-weight: 500; margin-bottom: 6px; }
.form-group input,
.form-group textarea {
    width: 100%; padding: 13px 16px;
    font-size: 15px; border: 1px solid #d2d2d7;
    border-radius: 10px; font-family: inherit;
}
.form-group input:focus,
.form-group textarea:focus {
    outline: none;
    border-color: #0071e3;
    box-shadow: 0 0 0 4px rgba(0,113,227,0.1);
}
.form-group textarea { resize: vertical; min-height: 160px; }

.submit-button {
    width: 100%; padding: 15px;
    background: #0071e3; color: #fff;
    border: none; border-radius: 980px;
    font-size: 17px; cursor: pointer;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}
.submit-button:hover { background: #0077ed; transform: scale(1.02); }
```

### Immagine Esemplificativa
```
Contatti
Hai domande o vuoi collaborare?

┌────────────────────┐  ┌─────────────────────────────────────┐
│ [📧] Email         │  │  Nome                               │
│   traerete@...     │  │  [________________________]         │
│                    │  │  Cognome                            │
│ [📞] Telefono      │  │  [________________________]         │
│   +39 011 000 0000 │  │  Email                              │
│                    │  │  [________________________]         │
│  [icone cerchi     │  │  Messaggio                          │
│   46px blu]        │  │  [                         ]        │
│                    │  │  [  min-height: 160px       ]       │
│   [largh. 320px]   │  │         [ Invia messaggio ]         │
└────────────────────┘  └─────────────────────────────────────┘
     colonna sinistra             colonna destra (card bianca)
```

---

## 10. Footer

### Requisito Funzionale
Il footer è presente identico in tutte le pagine del sito. È diviso in 3 colonne: **Link utili** (navigazione rapida), **Seguici** (link ai social), **Newsletter** (form di iscrizione con campo email e pulsante). In fondo c'è una riga con il copyright.

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
- Sfondo: blu scuro/grafite `#1f2937`, `padding-top: 56px`
- Griglia 3 colonne: `grid-template-columns: 1fr 1fr 1.6fr`, `gap: 48px`
- Intestazioni `h5`: `11px`, tutto maiuscolo, `letter-spacing: 0.1em`, `opacity: 0.7`
- Link: bianco al 75% `rgba(255,255,255,0.75)`, diventano bianchi pieni all'hover
- Form newsletter: input e pulsante affiancati in riga, sfondo input glass `rgba(255,255,255,0.08)`
- Riga copyright: separatore bianco, testo `12px`, bianco al 40%
- Su mobile (≤768px): le 3 colonne si impilano in una sola colonna, form newsletter in colonna verticale

### Codice CSS
```css
footer {
    background-color: #1f2937;
    color: #ffffff;
    padding: 56px 0 0;
    border-top: 1px solid rgba(255,255,255,0.08);
}

.footer-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1.6fr;
    gap: 48px;
    padding-bottom: 48px;
}

.footer-col h5 {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    opacity: 0.7;
    margin-bottom: 20px;
}

.footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 10px; }
.footer-col ul li a,
.footer-social a { color: rgba(255,255,255,0.75); font-size: 14px; }
.footer-col ul li a:hover,
.footer-social a:hover { color: #ffffff; }

.newsletter-form { display: flex; gap: 8px; }
.newsletter-form input[type="email"] {
    flex: 1; padding: 10px 14px; font-size: 14px;
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 8px;
    background: rgba(255,255,255,0.08);
    color: #ffffff;
}
.newsletter-form button {
    padding: 10px 18px;
    background: #0071e3; color: #fff;
    border: none; border-radius: 8px;
    font-size: 14px; cursor: pointer;
}

.footer-bottom { border-top: 1px solid rgba(255,255,255,0.08); padding: 20px 0; text-align: center; }
.footer-bottom p { font-size: 12px; color: rgba(255,255,255,0.4); }
```

### Immagine Esemplificativa
```
┌─────────────────────────────────────────────────────────────────┐  ← sfondo #1f2937
│                                                                 │
│  LINK UTILI          SEGUICI         NEWSLETTER                 │
│  Home                Twitter         Iscriviti alla nostra      │
│  Articoli            Facebook        newsletter!               │
│  Chi siamo           Instagram       [ email... ] [Iscriviti]  │
│  Contatti                                                       │
│                                                                 │
│ ─────────────────────────────────────────────────────────────── │
│           © 2026 Tra Rete e Realtà. Tutti i diritti riservati. │
└─────────────────────────────────────────────────────────────────┘
```

---

## 11. Responsive Mobile

### Requisito Funzionale
Il sito si adatta automaticamente agli schermi con larghezza ≤768px tramite una media query. Tutti gli elementi ridimensionano font, padding e layout per garantire leggibilità e usabilità su smartphone.

### Principali adattamenti mobile

| Elemento | Desktop | Mobile (≤768px) |
|---|---|---|
| Header altezza | 48px | 44px |
| Logo font | 28px | 22px |
| Nav gap | 32px | 16px |
| Hero altezza min | 650px | 500px |
| Titolo hero | 64px | 40px |
| Testo hero | 28px | 21px |
| Immagine in evidenza | 420px | 280px |
| Titolo in evidenza | 40px | 28px |
| Griglia articoli | 2 colonne | 1 colonna |
| Immagine card piccola | 280px | 220px |
| Titolo pagine | 56px | 40px |
| Immagine articolo singolo | 480px | 280px |
| Titolo articolo | 48px | 32px |
| Immagine profilo chi siamo | 240px | 180px |
| Layout contatti | 2 colonne affiancate | 1 colonna |
| Form commento Nome/Email | affiancati | in colonna |
| Footer griglia | 3 colonne | 1 colonna |
| Form newsletter | riga | colonna |

### Codice CSS (estratto)
```css
@media (max-width: 768px) {
    header .logo { font-size: 22px; }
    header nav ul { gap: 16px; }

    .hero { min-height: 500px; padding: 80px 0; }
    .hero-content h2 { font-size: 40px; }

    .articles-grid { grid-template-columns: 1fr; }

    .contact-wrapper { flex-direction: column; }
    .contact-left { width: 100%; }

    .comment-form .form-row { flex-direction: column; }

    .footer-grid { grid-template-columns: 1fr; }
    .newsletter-form { flex-direction: column; }
}
```

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

Il sito usa il **font di sistema** per garantire velocità e coerenza con il dispositivo dell'utente:

```css
font-family: -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'Segoe UI', Arial, sans-serif;
```

| Elemento | Dimensione | Peso |
|---|---|---|
| Titolo hero `h2` | 64px | 700 (grassetto) |
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
