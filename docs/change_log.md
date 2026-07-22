# Change Log

## 2026-07-22
**Session**: Aggiornamento alla versione v1.33.1 (Conversation ID: 0a95585e-6420-43d9-9097-36553dbfa08e)

**Work Done**:
- **Aggiornamento Upstream**: Eseguito il merge dei commit upstream (135 nuovi commit) da `origin/main` (tag **v1.33.1**) nel branch `feature/italian-localization`.
- **Risoluzione Conflitti**: Risolti i conflitti di merge su `.swiftlint.yml` (combinando le regole di esclusione) e sui file di localizzazione `.xcstrings` tramite uno script Python personalizzato per preservare le traduzioni italiane.
- **Localizzazione**: Analizzato e integrato il supporto completo all'italiano (aggiunte 61 nuove chiavi in totale: 57 su `Localizable.xcstrings` e 4 su `Main.xcstrings`), raggiungendo nuovamente il **100%** di copertura per le funzionalità del nuovo gestore estensioni e degli Strumenti di scrittura (Writing Tools).
- **Build & Installazione**: Compilato con successo in configurazione `Release` con override della firma digitale ed eseguita l'installazione locale della nuova versione in `/Applications/MarkEdit.app`.

**Key Changes**:
- Integrazione di tutte le migliorie della v1.33.1, tra cui il supporto iniziale per macOS Golden Gate, il ripristino di Writing Tools e il nuovo gestore estensioni ("Gestisci estensioni…").
- Copertura totale del localizzatore italiano per tutte le nuove voci dell'interfaccia utente.

**Outcome**:
- MarkEdit.app v1.33.1 installato e funzionante con traduzioni in italiano complete al 100%.

## 2026-05-20
**Session**: Aggiornamento alla versione v1.32.1 (Conversation ID: 448022bb-4d33-4a95-a417-426c0e486132)

**Work Done**:
- **Aggiornamento Upstream**: Eseguito il merge pulito (senza conflitti) delle novità della versione **v1.32.1** (`origin/main`) nel branch di localizzazione `feature/italian-localization`.
- **Localizzazione**: Verificato il mantenimento della copertura al **100%** delle traduzioni in italiano.
- **Fix Configurazione**: Risolto un errore bloccante di SwiftLint aggiungendo la directory `BuildOutput` all'elenco `excluded` del file `.swiftlint.yml`, prevenendo controlli stilistici errati sulle classi generate automaticamente da Xcode.
- **Build**: Eseguite con successo le compilazioni sia `Debug` che `Release` tramite `xcodebuild` con override locale della firma digitale.
- **Installazione**: Aggiornata l'applicazione installata in `/Applications/MarkEdit.app` alla versione **1.32.1**.

**Key Changes**:
- Integrazione di tutte le migliorie upstream della v1.32.1 (inclusa la transizione a `EditorPreloader` e l'aggiunta di `FileDrop`).
- Preservata la localizzazione italiana nativa in tutti i file `.xcstrings` e nel progetto Xcode (`knownRegions`).

**Outcome**:
- MarkEdit.app v1.32.1 installato e perfettamente funzionante con localizzazione italiana completa.

## 2026-04-30
**Session**: Esito Pull Request #1397 (Conversation ID: 448022bb-4d33-4a95-a417-426c0e486132)

**Work Done**:
- Verificato lo stato della Pull Request ufficiale su `MarkEdit-app/MarkEdit`.
- Analizzato il feedback del manutentore (Rex Detiger / cyanzhong).

**Outcome**:
- **PR #1397 Chiusa (Rejected)**: Il manutentore ha declinato l'integrazione della localizzazione italiana per evitare l'onere di manutenzione a lungo termine e per la difficoltà di revisionare una lingua che non conosce.
- **Decisione**: In fase di valutazione ("pensiamoci e poi decidiamo"). Al momento il supporto per l'italiano resta esclusivo del nostro fork `MarkEdit-ita`.

## 2026-04-29
**Session**: Aggiornamento Preview v1.7.0 + PR Localizzazione Italiana (Conversation ID: 0488d643-a108-40c4-a252-f5b4c96360e5)

**Work Done**:
- Aggiornata l'estensione di anteprima (`markedit-preview.js`) alla versione 1.7.0.
- **Build**: Compilazione dell'applicazione eseguita con successo in configurazione `Release`.
- **Installazione**: Nuova versione di MarkEdit.app (v1.32.0) installata in `/Applications/`.
- **Audit traduzioni**: Analisi completa della copertura italiana su tutti i file `.xcstrings`.
- **Completamento traduzioni**: Aggiunte 14 stringhe mancanti per raggiungere il 100% di copertura.
- **Fix**: Corretti format specifiers posizionali (%1$@, %2$@) e rimosse 6 chiavi duplicate da merge precedente.
- **Pull Request**: Creata PR #1397 su `MarkEdit-app/MarkEdit` per l'aggiunta ufficiale della lingua italiana.

**Key Changes**:
- PR trasparente: dichiarato esplicitamente che le traduzioni sono generate da LLM.
- Copertura 100%: Localizable (197), Main (190), AppShortcuts (4), FinderExtension (3).
- Aggiunto `it` a `knownRegions` nel file di progetto Xcode.

**Outcome**:
- PR chiusa dal manutentore il 29/04/2026 (non accettata per burden di manutenzione).
- Versione con localizzazione italiana compilata e installata localmente in `/Applications/MarkEdit.app`.

## 2026-04-28
**Session**: Aggiornamento upstream del fork di MarkEdit (Conversation ID: 0488d643-a108-40c4-a252-f5b4c96360e5)

**Work Done**:
- Recuperato l'ultimo codice del repository originale di MarkEdit tramite `git pull origin main`.
- Gestito i merge conflict sorti durante l'aggiornamento.
- **Build**: Compilazione completata con successo (v1.32.0).
- **Risoluzione Bug**: Corretto errore di sintassi nel file `.swiftlint.yml` (chiave `excluded` duplicata) che bloccava la build.
- **Localizzazione**: Verificate e integrate le traduzioni italiane custom con le nuove stringhe upstream.

## Dettagli Tecnici
- **App Path**: `BuildOutput/Build/Products/Release/MarkEdit.app`
- **SwiftLint**: Risolto il blocco causato dalla configurazione YAML non valida.
- **Xcodebuild**: Utilizzato con override della firma digitale per build locali non distribuibili.

**Key Changes**:
- Risolti i conflitti per il file `MarkEditMac/Modules/Sources/AppKitControls/LabeledSearchField.swift` mantenendo la logica upstream più recente.
- Unito in modo automatico (tramite script Python personalizzato) le localizzazioni e le traduzioni nei file `MarkEditMac/Resources/Localizable.xcstrings` e `MarkEditMac/mul.lproj/Main.xcstrings` per garantire che le stringhe italiane aggiunte localmente non andassero perse a favore del nuovo codice in inglese, ma combinandole assieme.
- Pulito e ripristinato l'albero di lavoro (`working tree`) alla normalità mantenendo le estensioni aggiuntive (`estenzioni/`).

**Outcome**:
- Aggiornamento completato con successo senza perdita di traduzioni o customizzazioni. Il progetto `MarkEdit-ita` è ora allineato alla versione più recente.
