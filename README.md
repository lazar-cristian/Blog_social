# PROTOTIPAZIONE BLOG

## Titolo del blog
**"Tra Rete e Realtà"**

## Tema
Consapevolezza nell'uso dei social media, impatto degli algoritmi e rapporto tra vita digitale e vita reale.

## Stile
Moderno, serio e minimal con estetica ispirata alle interfacce editoriali contemporanee: layout pulito, tipografia leggibile, card arrotondate e forte attenzione al contrasto visivo nelle sezioni principali.

---

## STRUTTURA GENERALE DEL SITO
Il sito è composto da **6 pagine HTML**:

- `index.html` (Home)
- `articoli.html`
- `articolo-algoritmi.html`
- `articolo-detox.html`
- `chisiamo.html`
- `contatti.html`

Tutte le pagine condividono una base comune:

- **Header sticky** in alto con logo e menu di navigazione.
- **Contenuto centrale** gestito tramite `.container` con larghezza massima ~980/1024 px e centrato.
- **Footer** presente in ogni pagina, coerente con il resto del progetto.

Il layout è ordinato e realizzato con HTML semantico (`header`, `nav`, `main`, `section`, `article`, `footer`) e un unico foglio di stile condiviso (`style.css`).

---

## HEADER
### Struttura
Nella parte superiore è presente una barra con:

- A sinistra: logo testuale **"Tra Rete e Realtà"**.
- A destra: menu orizzontale con voci:
  - Home
  - Articoli
  - Chi siamo
  - Contatti

Ogni voce è cliccabile e collega alla rispettiva pagina.

### Grafica attuale

- Sfondo: bianco traslucido con effetto blur (stile glass).
- Testo: grigio scuro.
- Font: sans-serif di sistema moderno.
- Posizionamento: **sticky** in alto.
- Separazione: bordo inferiore sottile.

### Interazione hover/active

- Le voci del menu aumentano la visibilità in hover/active tramite variazione di opacità.
- Il logo ha un leggero effetto di scala in hover.

---

## HOMEPAGE (`index.html`)
### Sezione 1 – Hero
Subito sotto l'header è presente una hero con:

- Titolo centrale di grande impatto.
- Testo introduttivo sul tema del blog.
- Bottone CTA: **"Esplora gli articoli"**.

La sezione usa:

- Background fotografico con overlay scuro.
- Effetto parallax leggero via JavaScript.
- Tipografia ampia e ad alto contrasto.

### Sezione 2 – Articolo in evidenza
Box centrale con:

- Immagine grande.
- Titolo dell'articolo.
- Introduzione breve.
- Pulsante/Link **"Leggi l'articolo"**.

Card con bordi arrotondati, ombra e hover avanzato.

### Sezione 3 – Altri articoli
Sotto l'articolo in evidenza compaiono due card affiancate con:

- Immagine
- Titolo
- Descrizione breve
- Link all'articolo completo

Layout realizzato con griglia/flex, mantenendo ordine e leggibilità.

---

## PAGINE ARTICOLI
Le pagine articolo (`articoli.html`, `articolo-algoritmi.html`, `articolo-detox.html`) contengono:

- Titolo articolo.
- Data di pubblicazione.
- Immagine principale.
- Testo in paragrafi con sottosezioni.

`articoli.html` funge da pagina editoriale principale con un articolo completo in evidenza e ulteriori anteprime cliccabili verso gli articoli dedicati.

---

## PAGINA "CHI SIAMO" (`chisiamo.html`)
Contiene una presentazione del progetto con:

- Titolo di sezione.
- Struttura in due colonne (immagine + testo descrittivo).
- Focus su obiettivo del blog: promuovere un uso più consapevole dei social.

Layout semplice e coerente con il resto del sito.

---

## PAGINA CONTATTI (`contatti.html`)
Include:

- Titolo della sezione contatti.
- Modulo verticale con campi:
  - Nome
  - Email
  - Messaggio
- Pulsante di invio.

Il form è progettato come interfaccia front-end pulita e ordinata.

---

## FOOTER
Presente in tutte le pagine con contenuto centrato e tono editoriale.

Elementi principali:

- Copyright 2026 **Tra Rete e Realtà**.
- Breve frase descrittiva del progetto.

Stile coerente con il design generale del sito.

---

## STILE GENERALE DEL BLOG
### Palette prevalente

- Bianco e grigi chiari per le superfici.
- Grigio scuro/nero per tipografia.
- Blu come colore d'accento (CTA e stati interattivi).

### Caratteristiche visive

- Design moderno e minimal.
- Elevata leggibilità tipografica.
- Card con bordi arrotondati e ombre leggere.
- Micro-interazioni semplici (hover, transizioni), senza effetti eccessivi.

Il progetto è strutturato per essere facilmente mantenibile con HTML/CSS/JS base, mantenendo una presentazione professionale e coerente su tutte le pagine.
