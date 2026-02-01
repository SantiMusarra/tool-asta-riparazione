# 🎯 Asta di Riparazione - Fantacalcio Tool

Tool interattivo per gestire l'asta di riparazione del fantacalcio. **100% browser, nessuna installazione!**

## 📋 Descrizione

Pagina HTML standalone che elabora la lista dei calciatori della tua lega e fornisce:
- 💰 Budget disponibile per ogni fantasquadra (configurabile)
- 🔄 Gestione svincoli con recupero crediti automatico
- ⭐ Sistema preferenze personali (1-5 stelle)
- 🆕 Evidenziazione nuovi arrivi dal mercato
- 📊 Elenco calciatori svincolati suddivisi per ruolo con filtri avanzati
- 💾 Persistenza delle selezioni nel browser (per lega)
- 🔒 Tutti i dati elaborati localmente (privacy garantita)

---

## 🚀 Utilizzo

### Zero installazione!

1. **Apri** `index.html` nel browser (o [usa la versione online](#-hosting))
2. **Carica** il file Excel della tua lega (drag & drop o click)
3. **Fatto!** La pagina elabora tutto automaticamente

> 💡 Funziona completamente offline! Nessun dato viene inviato a server esterni.

---

## 🌐 Hosting

### Opzione 1: Firebase Hosting (Consigliato)
```bash
npm install -g firebase-tools
firebase login
cd /percorso/asta_riparazione
firebase init hosting  # Directory: . | SPA: No | Overwrite: No
firebase deploy
```
URL: `https://tuo-progetto.web.app`

### Opzione 2: GitHub Pages
1. Crea un repository su GitHub
2. Pusha il codice
3. Settings → Pages → Source: main branch
4. URL: `https://username.github.io/repo-name`

### Opzione 3: Netlify Drop
1. Vai su [app.netlify.com/drop](https://app.netlify.com/drop)
2. Trascina la cartella del progetto
3. Ottieni subito un URL pubblico

### Opzione 4: Condivisione diretta
Essendo un singolo file HTML, puoi semplicemente inviare `index.html` via email/chat!

---

## 📁 Struttura Progetto

```
asta_riparazione/
├── index.html    ← App standalone (apri questo!)
└── README.md     ← Documentazione
```

---

## 📥 Input

### File richiesto
- **Formato:** Excel (.xlsx o .xls)
- **Origine:** Scaricato da [leghe.fantacalcio.it](https://leghe.fantacalcio.it/)
- **Importante:** Non rinominare il file! Il nome della lega viene estratto automaticamente

### Come ottenere il file
1. Accedi a [leghe.fantacalcio.it](https://leghe.fantacalcio.it/)
2. Seleziona la tua lega
3. Vai in **Lista Svincolati**
4. Togli la spunta da "Solo svincolati"
5. Clicca **Scarica** → **Lista completa**

### Colonne richieste

| Colonna | Descrizione |
|---------|-------------|
| `Nome` | Nome del calciatore |
| `R.` | Ruolo (P/D/C/A) |
| `Sq.` | Squadra di Serie A |
| `PGv` | Partite giocate (a voto) |
| `MV` | Media voto |
| `FM` | FantaMedia |
| `QUOT.` | Quotazione attuale |
| `FantaSquadra` | Fantasquadra (vuoto se svincolato) |
| `Costo` | Costo all'asta iniziale |
| `Fuori lista` | `*` se fuori lista |

---

## 🖥️ Interfaccia

### Tab disponibili

| Tab | Contenuto |
|-----|-----------|
| **🏠 Home** | Budget squadre, gestione svincoli, ricerca rapida, riepilogo |
| **⚙️ Configurazione** | Impostazioni lega, regole rimborso, caricamento mercato |
| **🧤 Portieri** | Portieri svincolati con filtri |
| **🛡️ Difensori** | Difensori svincolati con filtri |
| **⚽ Centrocampisti** | Centrocampisti svincolati con filtri |
| **🎯 Attaccanti** | Attaccanti svincolati con filtri |

### Simboli e badge

| Simbolo | Significato |
|---------|-------------|
| ⚠️ | Fuori Lista (non acquistabile) |
| 🆕 NEW | Nuovo arrivo dal mercato |
| ⭐ | Preferenza personale (1-5 stelle) |
| 🔓 | Già svincolato (nella ricerca rapida) |
| ✅ Riga verde | Giocatore svincolato |
| 🔄 Rilasciato | Giocatore rilasciato da una fantasquadra |

---

## ⚙️ Configurazione Lega

### Parametri Budget

| Parametro | Default | Descrizione |
|-----------|---------|-------------|
| Budget iniziale | 500 | Crediti iniziali per squadra |
| Crediti aggiuntivi | 50 | Crediti extra per riparazione |
| Budget per squadra | Auto | `Budget iniziale - Costo rosa` |

### Regole Rimborso

| Parametro | Default | Opzioni |
|-----------|---------|---------|
| Rimborso standard | 50% | 0%, 25%, 50%, 75%, 100% |
| Rimborso fuori lista | 100% | 0%, 50%, 100% |
| Arrotondamento | Per difetto | Difetto, Eccesso, Matematico |

---

## 🆕 Nuovi Arrivi dal Mercato (Opzionale)

Puoi caricare i trasferimenti ufficiali per evidenziare i nuovi acquisti:

1. Vai su [fantacalcio.it/trasferimenti-ufficiali](https://www.fantacalcio.it/calciomercato/trasferimenti-ufficiali)
2. Salva la pagina come HTML (`Cmd+S` / `Ctrl+S`)
3. Carica il file nella sezione Configurazione

I nuovi arrivi verranno evidenziati con il badge **NEW** nelle tabelle.

---

## 🔄 Gestione Svincoli

### Metodo 1 - Ricerca rapida
1. Usa la barra "🔍 Cerca calciatore..."
2. Seleziona dall'autocomplete
3. Clicca "⚡ Svincola" (o "❌ Annulla" se già svincolato)

### Metodo 2 - Dalla rosa
1. Espandi la sezione della squadra
2. Spunta/deseleziona la checkbox del calciatore
3. Il budget si aggiorna automaticamente

### Giocatori rilasciati
Quando svincoli un giocatore che non è fuori lista, questo torna disponibile nelle tabelle degli svincolati con il badge "Rilasciato da [Squadra]".

---

## 📊 Indice Affidabilità

**Formula:** `PGv × FM`

Premia i calciatori che:
- ✅ Giocano con continuità (alto PGv)
- ✅ Hanno buone prestazioni (alta FM)

---

## 🔍 Filtri Disponibili

Ogni tab dei ruoli include:
- 🔎 Ricerca per nome
- 🏟️ Filtro per squadra Serie A
- 📈 FM minima
- ⚽ PGv minimo
- ⭐ Filtro preferiti (1-5 stelle)
- 🆕 Solo nuovi arrivi
- 🔄 Filtro rilasciati

Le tabelle sono **ordinabili** cliccando sulle intestazioni.

---

## 💾 Persistenza Dati

I dati sono salvati nel browser e associati al nome della tua lega:

| Dato | Persistenza |
|------|-------------|
| Svincoli selezionati | ✅ Per lega |
| Configurazione budget | ✅ Per lega |
| Regole rimborso | ✅ Per lega |
| Preferenze giocatori | ✅ Per lega |
| Nuovi arrivi mercato | ✅ Per lega |

> 💡 Puoi gestire più leghe! Ogni file caricato mantiene i propri dati separati.

---

## 📱 Compatibilità

| Dispositivo | Supporto |
|-------------|----------|
| Desktop/Laptop | ✅ Ottimale |
| Tablet | ⚠️ Funziona, layout adattato |
| Smartphone | ⚠️ Funziona, esperienza limitata |

> Il tool è ottimizzato per schermi larghi a causa delle tabelle estese.

---

## 🔒 Privacy

- ✅ **Nessun server** - Tutti i dati elaborati localmente
- ✅ **Nessun tracciamento** - Zero analytics o cookies di terze parti
- ✅ **Offline** - Funziona senza connessione internet
- ✅ **Open source** - Codice ispezionabile

---

## 🔄 Workflow Tipico

1. 📥 Scarica il file Excel aggiornato da leghe.fantacalcio.it
2. 🌐 Apri il tool (locale o online)
3. 📂 Carica il file Excel
4. ⚙️ Configura budget e regole (solo la prima volta)
5. 🔄 Gestisci gli svincoli
6. 📋 Consulta gli svincolati disponibili
7. 🔁 Ripeti quando i dati cambiano (le selezioni persistono!)

---

## 📄 Licenza

MIT License - Usa liberamente!