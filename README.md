# Bollettini TPS

Pagina web che sovrappone i rapporti (PDF) al modulo del rapporto di lavoro TPS vuoto e crea un unico PDF, in formato A5 (o A4), da stampare o inviare.

- I PDF vengono elaborati solo nel browser di chi usa la pagina: nessun file viene caricato su GitHub o altrove.
- `index.html`: la pagina.
- `bollettino-vuoto.pdf`: il modulo vuoto.

## Come si usa

1. Trascina i PDF dei rapporti nel riquadro (anche più file; ogni pagina diventa un bollettino).
2. Controlla l'anteprima a destra (frecce ‹ › per scorrere le pagine).
3. Scegli il formato **A5** (predefinito) o **A4** e clicca **Scarica PDF**.
4. In stampa scegli carta **A5** e **Dimensioni effettive / 100%**.

## Regola posizione e modulo

Si apre cliccando la freccetta in fondo al passo 2. Normalmente non serve: i valori sono già tarati sul modulo. Serve in due casi.

### 1. Il testo non cade al posto giusto

Il rapporto è come un foglio trasparente con solo il testo, appoggiato sopra il modulo vuoto. I due campi in millimetri dicono di quanto spostarlo:

- **Orizzontale (mm):** numero più alto → testo **a destra**; più basso → **a sinistra**.
- **Verticale (mm):** numero più alto → testo **in alto**; più basso → **in basso**.

L'anteprima si aggiorna subito mentre cambi il numero. Esempio: se le date stanno 2 mm troppo in basso rispetto alle caselle Lu–Do, porta il verticale da 16.6 a 18.6.

I millimetri si riferiscono al modulo a grandezza piena (un po' più grande dell'A5): prova, guarda l'anteprima e aggiusta.

- **Ripristina posizione** riporta i valori di partenza: 24.8 (orizzontale) e 16.6 (verticale).
- La correzione resta salvata **solo nel browser di chi la fa**: non cambia per gli altri colleghi.

### 2. Usare un altro modulo vuoto

- **Cambia modulo vuoto…** permette di scegliere un altro PDF (es. una nuova scansione). Vale solo finché la pagina resta aperta.
- **Usa modulo originale** torna a quello standard.

Con una scansione nuova il modulo potrebbe essere leggermente spostato o storto: ritocca i due valori in mm finché il testo torna al suo posto.

## Aggiornare il sito (per chi gestisce la repository)

- **Cambiare il modulo per tutti:** nella repository clicca **Add file → Upload files**, carica il nuovo PDF con lo **stesso nome** `bollettino-vuoto.pdf` e clicca **Commit changes**. Il sito si aggiorna in 1–2 minuti.
- **Cambiare la posizione di partenza per tutti:** i valori predefiniti sono in `index.html`, nella riga `DEF={dx:24.8,dy:16.6}` (dx = orizzontale, dy = verticale, in mm). Modificali e salva con **Commit changes**.
