# Task Ricorrenti — MarkEdit-ita

Questo file contiene le azioni da eseguire **ad ogni apertura di sessione** su questo progetto.

---

## ✅ Checklist di Inizio Sessione

### 1. Controlla lo stato della PR #1397 (Localizzazione Italiana)

**URL**: https://github.com/MarkEdit-app/MarkEdit/pull/1397

Verificare lo stato con:
```bash
gh pr view 1397 --repo MarkEdit-app/MarkEdit --json state,mergedAt,closedAt,title
```

**Possibili scenari:**

| Stato | Azione |
|-------|--------|
| `OPEN` | Nessuna azione. Monitorare eventuali commenti o richieste di modifica. |
| `MERGED` | 🎉 Aggiornare `main` locale con `git pull origin main`. La prossima build includerà la localizzazione ufficiale. |
| `CLOSED` (rifiutata) | Leggere i motivi. Valutare se fare correzioni e riaprire. |

---

### 2. Controlla se ci sono nuove release upstream di MarkEdit

```bash
gh release view --repo MarkEdit-app/MarkEdit
```

Se c'è una versione più recente:
1. Fare `git pull origin main` per sincronizzare il fork locale.
2. Verificare se ci sono nuove stringhe da tradurre in italiano.
3. Fare build + installazione locale.

---

### 3. Controlla aggiornamenti di MarkEdit-preview

```bash
gh release list --repo MarkEdit-app/MarkEdit-preview --limit 1
```

Se c'è una versione più recente dell'estensione di anteprima:
1. Aggiornare `estenzioni/markedit-preview.js` scaricando il nuovo bundle.
2. Rifare la build e reinstallare.

---

## 📌 Riferimenti Rapidi

| Risorsa | Link |
|---------|------|
| PR Localizzazione IT | https://github.com/MarkEdit-app/MarkEdit/pull/1397 |
| Fork personale | https://github.com/luciano99999/MarkEdit |
| Release ufficiali MarkEdit | https://github.com/MarkEdit-app/MarkEdit/releases |
| Release MarkEdit-preview | https://github.com/MarkEdit-app/MarkEdit-preview/releases |
| Branch locale IT | `feature/italian-localization` |
| App installata | `/Applications/MarkEdit.app` (v1.37.0 + IT) |
