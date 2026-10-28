# mAiTV

La home in stile smart TV che riunisce tutti i tuoi servizi di streaming.

## Cosa c'è nella cartella

| File | A cosa serve |
|---|---|
| `index.html` | L'app vera e propria |
| `manifest.json` | Dice al sistema che mAiTV è un'app installabile: nome, icona, colori, schermo intero |
| `sw.js` | Service worker: tiene la home in memoria così si apre subito, anche offline |
| `icons/` | Le icone dell'app (normali, "maskable" per Android, Apple) |

## Metterla online gratis (5 minuti)

Una PWA si installa solo se è servita in **https**. Due modi semplici:

### Netlify Drop (il più veloce)
1. Vai su https://app.netlify.com/drop
2. Trascina dentro **l'intera cartella `maitv`**
3. Ti dà subito un indirizzo tipo `https://nome-a-caso.netlify.app`. Puoi rinominarlo in `maitv.netlify.app` dalle impostazioni del sito.

### GitHub Pages
1. Crea un repository su GitHub (es. `maitv`) e carica tutti i file
2. Settings → Pages → Source: branch `main`, cartella `/ (root)` → Save
3. Dopo un minuto l'app è su `https://tuonome.github.io/maitv/`

## Installarla

- **PC (Chrome o Edge):** apri l'indirizzo e clicca l'icona di installazione nella barra degli indirizzi.
- **Android:** Chrome → menu ⋮ → "Installa app".
- **iPhone / iPad:** Safari → Condividi → "Aggiungi alla schermata Home".
- **TV Android / Google TV / Fire TV:** apri l'indirizzo dal browser della TV (es. Silk o TV Bro). Le frecce del telecomando muovono la selezione, OK apre l'app.

## Provarla sul tuo computer prima di pubblicarla

Il service worker non parte aprendo il file con doppio clic. Avvia un piccolo server nella cartella:

```
python3 -m http.server 8000
```

poi apri http://localhost:8000

## Aggiornarla

Dopo aver modificato i file, cambia `maitv-v1` in `maitv-v2` dentro `sw.js`, così chi l'ha installata riceve la nuova versione.
