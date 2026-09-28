# Bollettini TPS

Pagina web che sovrappone i rapporti (PDF) al modulo del rapporto di lavoro TPS vuoto e crea un unico PDF di fogli A4 verticali, con un bollettino A5 per foglio (metà alta, bordi di 0,5 cm), da stampare o inviare.

- I PDF vengono elaborati solo nel browser di chi usa la pagina: nessun file viene caricato su GitHub o altrove.
- `index.html`: la pagina.
- `bollettino-vuoto.pdf`: il modulo vuoto.

## Come si usa

1. Trascina i PDF dei rapporti nel riquadro (anche più file; ogni pagina diventa un bollettino).
2. Controlla l'anteprima a destra (frecce ‹ › per scorrere le pagine).
3. *(Facoltativo)* Nel riquadro **Compila ore e luogo** scegli il bollettino e inserisci cantiere/oggetto, orari (mattino e pomeriggio, dalle/alle), luogo di lavoro e centro di costo. Gli orari si possono scrivere anche veloci: `7` → 07:00, `1730` o `17.30` → 17:30. Totale del giorno e della settimana sono calcolati in centesimi (7:30 → 7.50), senza supplementi; un turno oltre la mezzanotte (22:00–06:00) conta normalmente (8 ore). Luogo e centro di costo "della settimana" vengono stampati nei giorni con ore; un valore scritto nel singolo giorno ha la precedenza. **Copia gli orari di Lu su Ma–Ve** velocizza le settimane uguali.
4. Clicca **Scarica PDF**: ogni bollettino occupa la metà alta di un foglio A4, a tutta area A5 con bordi di 0,5 cm.
5. In stampa scegli carta **A4 verticale** e **Dimensioni effettive / 100%**. La linea tratteggiata a metà foglio indica dove tagliare per avere il bollettino A5.

## Regola posizione e modulo

Questo riquadro è **nascosto** ai colleghi: i valori sono già tarati sul modulo e normalmente non serve.

Per farlo comparire, aggiungi `#regola` in fondo al link: `https://goccia-sa.github.io/Bollettini-TPS/#regola`. Senza `#regola` la pagina usa sempre i valori predefiniti, anche se in precedenza qualcuno li aveva modificati nel suo browser.

Serve in due casi.

### 1. Il testo non cade al posto giusto

Il rapporto è come un foglio trasparente con solo il testo, appoggiato sopra il modulo vuoto. I due campi in millimetri dicono di quanto spostarlo:

- **Orizzontale (mm):** numero più alto → testo **a destra**; più basso → **a sinistra**.
- **Verticale (mm):** numero più alto → testo **in alto**; più basso → **in basso**.

L'anteprima si aggiorna subito mentre cambi il numero. Esempio: se le date stanno 2 mm troppo in basso rispetto alle caselle Lu–Do, porta il verticale da 16.6 a 18.6.

I millimetri si riferiscono al modulo a grandezza piena (un po' più grande del bollettino A5 stampato): prova, guarda l'anteprima e aggiusta.

- **Ripristina posizione** riporta i valori di partenza: 24.8 (orizzontale) e 16.6 (verticale).
- La correzione resta salvata **solo nel browser di chi la fa** e vale solo aprendo il link con `#regola`. Per renderla definitiva per tutti, vanno cambiati i valori predefiniti (vedi sotto).

### 2. Usare un altro modulo vuoto

- **Cambia modulo vuoto…** permette di scegliere un altro PDF (es. una nuova scansione). Vale solo finché la pagina resta aperta.
- **Usa modulo originale** torna a quello standard.

Con una scansione nuova il modulo potrebbe essere leggermente spostato o storto: ritocca i due valori in mm finché il testo torna al suo posto.

## Aggiornare il sito (per chi gestisce la repository)

- **Cambiare il modulo per tutti:** nella repository clicca **Add file → Upload files**, carica il nuovo PDF con lo **stesso nome** `bollettino-vuoto.pdf` e clicca **Commit changes**. Il sito si aggiorna in 1–2 minuti.
- **Cambiare la posizione di partenza per tutti:** i valori predefiniti sono in `index.html`, nella riga `DEF={dx:24.8,dy:16.6}` (dx = orizzontale, dy = verticale, in mm). Modificali e salva con **Commit changes**.
