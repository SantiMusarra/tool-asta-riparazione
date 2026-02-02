# 🏆 Fanta Rescue - Fantacalcio Tool

Tool gratuito per preparare l'asta di riparazione del Fantacalcio. **100% browser, nessuna installazione!**

## 📋 Cosa puoi fare

- Vedi le rose e i budget di tutte le squadre della lega
- Segna gli svincoli e calcola i rimborsi automaticamente
- Esplora gli svincolati per ruolo con statistiche e quotazioni
- Segna i tuoi preferiti e tieni traccia di chi è già stato preso
- Visualizza infortunati e nuovi arrivi dal mercato

> 🔒 **Privacy:** Tutto funziona nel browser, nessun dato viene inviato online.
> I dati non si sincronizzano tra dispositivi diversi.

---

## 🚀 Utilizzo

### Zero installazione!

1. **Apri** `index.html` nel browser (o [usa la versione online](#-hosting))
2. **Carica** il file Excel della tua lega (drag & drop o click)
3. **Fatto!** La pagina elabora tutto automaticamente

> 💡 Funziona completamente offline! 

---

## 📥 Come ottenere il file della lega

1. Apri il **sito web** [leghe.fantacalcio.it](https://leghe.fantacalcio.it/) (non l'app!)
2. Seleziona la tua lega dal menu in alto
3. Clicca su **Lista Calciatori**
4. Assicurati che "Solo svincolati" sia **disattivato**
5. Clicca **Scarica** → **Lista completa**

> ⚠️ **Non rinominare il file!** Il nome della lega viene estratto automaticamente dal nome del file.

---

## 🌐 Hosting

### Opzione 1: GitHub Pages (Consigliato)
1. Crea un repository su GitHub
2. Pusha il codice
3. Settings → Pages → Source: main branch
4. URL: `https://username.github.io/repo-name`

### Opzione 2: Netlify Drop
1. Vai su [app.netlify.com/drop](https://app.netlify.com/drop)
2. Trascina la cartella del progetto
3. Ottieni subito un URL pubblico

### Opzione 3: Condivisione diretta
Essendo un singolo file HTML, puoi semplicemente inviare `index.html` via email/chat!

---

## 📁 Struttura Progetto

```
fanta-rescue/
├── index.html           ← App standalone (apri questo!)
├── README.md            ← Documentazione
└── screenshots/         ← Screenshot per le istruzioni
    ├── step1-menu-lega.png
    ├── step1-menu-mobile.jpeg
    └── step2-scarica-lista.png
```

---

## 🖥️ Interfaccia

### Tab disponibili

| Tab | Contenuto |
|-----|-----------|
| **🏠 Home** | Budget squadre, gestione svincoli, ricerca rapida, riepilogo |
| **⚙️ Configurazione** | Impostazioni lega, regole rimborso, infortunati, trasferimenti |
| **🧤 Portieri** | Portieri svincolati con filtri |
| **🛡️ Difensori** | Difensori svincolati con filtri |
| **⚽ Centrocampisti** | Centrocampisti svincolati con filtri |
| **🎯 Attaccanti** | Attaccanti svincolati con filtri |

### Simboli e badge

| Simbolo | Significato |
|---------|-------------|
| ⚠️ | Fuori Lista (non acquistabile) |
| 🆕 NEW | Nuovo arrivo dal mercato |
| 🏥 INF | Giocatore infortunato |
| ⭐ | Preferenza personale (1-5 stelle) |
| 🔓 | Già svincolato (nella ricerca rapida) |
| PRESO | Acquistato da un'altra squadra |
| ✅ Riga verde | Giocatore svincolato |

---

## ⚙️ Configurazione

### Parametri Budget

| Parametro | Default | Descrizione |
|-----------|---------|-------------|
| Budget iniziale | 500 | Crediti iniziali per squadra |
| Crediti aggiuntivi | 50 | Crediti extra per riparazione |
| Budget per squadra | Auto | `Budget iniziale - Costo rosa` |

> ⚠️ Se ci sono stati scambi tra squadre durante la stagione, ricorda di correggere manualmente i budget residui!

### Regole Rimborso

| Parametro | Default | Opzioni |
|-----------|---------|---------|
| Rimborso standard | 50% | 0%, 25%, 50%, 75%, 100% |
| Rimborso fuori lista | 100% | 0%, 50%, 100% |
| Arrotondamento | Per difetto | Difetto, Eccesso, Matematico |

---

## 🏥 Infortunati (Opzionale)

Puoi caricare la lista degli infortunati per evidenziarli nelle tabelle:

### Metodo automatico (consigliato)
Clicca "🔄 Aggiorna automaticamente" nella sezione Configurazione.

### Metodo manuale
1. Vai su [fantacalcio.it/infortunati-serie-a](https://www.fantacalcio.it/infortunati-serie-a)
2. Salva la pagina come HTML (`Cmd+S` / `Ctrl+S`)
3. Carica il file nella sezione Configurazione

Gli infortunati verranno evidenziati con il badge **🏥 INF** e un tooltip con i dettagli.

---

## 🆕 Nuovi Arrivi dal Mercato (Opzionale)

Puoi caricare i trasferimenti ufficiali per evidenziare i nuovi acquisti:

### Metodo automatico (consigliato)
Clicca "🔄 Aggiorna automaticamente" nella sezione Configurazione.

### Metodo manuale
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
Quando svincoli un giocatore, questo torna disponibile nelle tabelle degli svincolati con il badge "Rilasciato da [Squadra]".

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
- ❌ Filtro acquistati
- 🏥 Filtro infortunati
- ✖ Pulisci filtri (reset ai valori default)

Le tabelle sono **ordinabili** cliccando sulle intestazioni. L'ordinamento viene mantenuto anche quando si assegnano le stelle.

> 💡 I giocatori con stelle (preferiti) appaiono sempre in cima alla tabella!

---

## 📊 Indice Affidabilità

**Formula:** `PGv × FM`

Premia i calciatori che:
- ✅ Giocano con continuità (alto PGv)
- ✅ Hanno buone prestazioni (alta FM)

---

## 💾 Persistenza Dati

| Dato | Persistenza |
|------|-------------|
| Svincoli selezionati | ✅ Per lega |
| Configurazione budget | ✅ Per lega |
| Regole rimborso | ✅ Per lega |
| Preferenze giocatori | ✅ Per lega |
| Giocatori acquistati | ✅ Per lega |
| Infortunati | ✅ Globale (tutte le leghe) |
| Nuovi arrivi mercato | ✅ Globale (tutte le leghe) |

> 💡 Puoi gestire più leghe! Ogni file caricato mantiene i propri dati separati.

> ⚠️ **No sync:** I dati sono salvati solo su questo dispositivo/browser. Se usi il tool da un altro dispositivo, dovrai ricaricare il file e rifare le selezioni.

---

## 📱 Compatibilità

| Dispositivo | Supporto |
|-------------|----------|
| Desktop/Laptop | ✅ Ottimale |
| Tablet | ⚠️ Funziona, layout adattato |
| Smartphone | ⚠️ Funziona, esperienza limitata |

> Il tool è ottimizzato per schermi larghi a causa delle tabelle estese.

> ⚠️ **Nota:** Questo tool è ottimizzato per la modalità **Classic**. La modalità **Mantra** potrebbe non essere completamente supportata.

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
5. 🏥 Carica infortunati e trasferimenti (opzionale, con auto-fetch)
6. 🔄 Gestisci gli svincoli
7. ⭐ Segna i tuoi preferiti
8. 📋 Consulta gli svincolati disponibili
9. 🔁 Ripeti quando i dati cambiano (le selezioni persistono!)

---

## 📄 Licenza

Questo progetto è rilasciato sotto licenza **GNU General Public License v3.0 (GPL-3.0)**.

Se distribuisci questo software o versioni modificate:
- Devi includere il codice sorgente o renderlo disponibile
- Devi mantenere la stessa licenza GPL-3.0
- Devi indicare le modifiche effettuate
- Devi mantenere gli avvisi di copyright originali

Per il testo completo della licenza, consulta: https://www.gnu.org/licenses/gpl-3.0.html

---
## ⚠️ Disclaimer
*Fanta Rescue non è affiliato con Fantacalcio.it o altre piattaforme ufficiali.*
