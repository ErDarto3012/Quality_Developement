# Quality Development — Appunti del corso UNICT

Questa repository raccoglie gli **appunti del corso UNICT _“Quality Development: how to properly write your project”_**, con esempi pratici, template riutilizzabili e workflow per migliorare **qualità del codice**, **automazione** e **rilascio**.  
Sono **note operative** per lo studio e l’applicazione immediata nei progetti.

---

## Lezioni e argomenti

### 🔹 Lezione 1 — Terminale e Bash
- Shell vs Bash vs Terminale, comandi base, script, variabili, redirezioni, pipe, alias, `.gitignore`.

### 🔹 Lezione 2 — Git: basi e flusso di lavoro
- Configurazione, `init/add/commit/status/log`, diff e ripristino file, branching, merge, revert e reset.

### 🔹 Lezione 3 — GitHub: repository e collaborazione
- Creare repo, primo push, aggiornare remote, clonare, Pull Request, cenni a fork e review.

### 🔹 Lezione 4 — Open Source e licenze
- Concetti OS, esempi (Android, BSD), licenze **MIT / Apache 2.0 / GPLv3 / LGPLv3 / AGPLv3**, community e opportunità.

### 🔹 Lezione 5 — Python essenziale
- Installazione, sintassi base, strutture dati, stile/indentazione, prime pratiche di qualità.

### 🔹 Lezione 6 — Software Testing
- Testing in Python, linting, unit test con `pytest`, coverage, integrazione nel flusso di sviluppo.

### 🔹 Lezione 7 — CI/CD e Pipeline
- Continuous Integration e Delivery, pipeline di build/test/deploy, esempi con **GitHub Actions**.

### 🔹 Lezione 8 — SOLID
- Principi **SRP, OCP, LSP, ISP, DIP** con esempi “bad vs good” per guidare refactoring e design.

### 🔹 Lezione 9 — Tools e Debugging
- Strumenti operativi, workflow riutilizzabili, **Docker / ghcr**, secrets, **GitHub Pages**, tecniche di debugging.

---

## Come scaricare la repository

```bash
# Clona via HTTPS
git clone https://github.com/<org-o-utente>/<repo>.git

# Oppure via SSH (dopo aver configurato la chiave SSH su GitHub)
git clone git@github.com:<org-o-utente>/<repo>.git

# Entra nella cartella del progetto
cd <repo>

# Verifica lo stato della working directory
git status
```

## Comandi Git/GitHub essenziali

```bash
# Configurazione globale
git config --global user.name "Nome Cognome"
git config --global user.email "tuaemail@example.com"
git config --global core.editor nano

# Mostra la configurazione corrente
git config --list
