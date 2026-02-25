# Echo Show Keep‑Alive for Home Assistant

Un **keep‑alive leggero e dark‑themed** progettato per impedire ai dispositivi **Amazon Echo Show** di chiudere automaticamente il browser quando visualizzano dashboard Home Assistant tramite iframe.

## 🚀 Il Problema
Gli Echo Show chiudono il browser (Silk/Firefox) dopo pochi minuti di inattività, interrompendo la visualizzazione delle dashboard di Home Assistant.

## 💡 La Soluzione
Questo progetto mantiene attiva la sessione del browser tramite:

- **Audio Heartbeat** – un file audio (`media.mp3`) riprodotto in loop.
- **Aggiornamenti del DOM** – orologio e data aggiornati ogni secondo per mantenere reattivo il rendering.
- **Interazione utente** – un singolo tap abilita l’audio (richiesto dalle policy autoplay moderne).

---

## 🛠️ Installazione

### 1. Carica i File
Carica i seguenti file nella cartella `www` di Home Assistant  
(di solito: `/config/www/echo-keepalive/`):

- `index.html`
- `media.mp3` (consigliata una traccia silenziosa)

### 2. Aggiungi alla Dashboard
Crea una card **Webpage** in Home Assistant con:

- **URL:** `/local/echo-keepalive/index.html`  
- **Aspect Ratio:** `100%` (o adattalo al tuo Echo Show)

---

## 📄 Utilizzo

1. Apri la dashboard sull’Echo Show.  
2. **Tocca una volta lo schermo.**  
   Serve per far partire l’audio non mutato (autoplay policies).  
3. Il testo dell’orologio diventerà **giallo (#ffc107)** → significa che il keep‑alive è attivo.

---

## 📂 Struttura della Cartella

```text
/config/www/echo-keepalive/
├── index.html
└── media.mp3
```

## ⚙️ Customization

### **Background**
The background color is set to `#111111` to blend seamlessly with Home Assistant's dark mode and help reduce display power consumption.

### **Localization**
Time and date formatting are configured for `it-IT` by default.  
You can change this by editing the `toLocaleTimeString()` and `toLocaleDateString()` settings inside `index.html`.

### **Appearance**
You can freely customize font sizes, colors, spacing, and overall layout by modifying the CSS section inside `index.html`.
