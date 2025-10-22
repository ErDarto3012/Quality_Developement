# Lezione 1 — Terminale

## Shell UNIX

L’uso della **shell UNIX** è obbligatorio per lavorare sui server.  
Nei server non è presente un’interfaccia grafica, quindi **il terminale è l’unico strumento disponibile**.  
Per questo motivo è importante saper usare **Git** da riga di comando.

### Differenza tra Shell e Bash

- Una **shell** è un interprete di comandi (come un linguaggio).
- **Bash** è una shell specifica che interpreta e adatta il linguaggio dei comandi.
- Il **terminale** è invece la finestra dove scriviamo i comandi.

## Bash
### **Cos’è Bash**
**Bash** è l’acronimo di **Bourne Again SHell**.  
È una **shell** — cioè un _interprete di comandi_ — che permette all’utente di comunicare con il sistema operativo **tramite testo**, senza bisogno di interfacce grafiche (GUI).

In pratica, Bash è l’ambiente in cui puoi **scrivere comandi**, **eseguire script**, **automatizzare processi** e **gestire file o programmi** direttamente dal terminale.

### **Differenza tra Bash, Shell e Terminale**

| Termine       | Significato                                                                                                             |
| ------------- | ----------------------------------------------------------------------------------------------------------------------- |
| **Shell**     | È un _interprete di comandi_: un programma che riceve istruzioni testuali e le esegue. Può essere Bash, Zsh, Fish, ecc. |
| **Bash**      | È una **specifica shell** (la più famosa su Linux e macOS). È l’evoluzione della “Bourne Shell” (sh).                   |
| **Terminale** | È l’applicazione grafica o finestra che **ospita la shell**. Serve solo per scrivere e visualizzare i comandi.          |

➡️ Quindi:

> Il **terminale** è la finestra.  
> La **shell** è il cervello che interpreta i comandi.  
> **Bash** è un tipo di shell.

### **A cosa serve Bash**
Bash serve a **controllare completamente il sistema operativo** da riga di comando.  
Con Bash puoi:
- Navigare tra **cartelle e file**
- Creare, modificare e cancellare file
- Installare o aggiornare software
- Gestire utenti e permessi
- Automatizzare attività ripetitive tramite **script**
- Amministrare **server remoti** (es. via SSH)
- Combinare più comandi insieme in **pipeline**

### **Come funziona Bash**
Ogni volta che scrivi un comando nel terminale:
1. Bash **interpreta** il comando (lo traduce in istruzioni comprensibili al sistema operativo).
2. Lo **esegue** tramite il kernel del sistema operativo.
3. Restituisce un **output** (risultato o messaggio di errore).

Esempio:
`ls -la`
- `ls` → comando (list directory)
- `-la` → opzioni (lista tutti i file in formato dettagliato)
- Bash lo interpreta e mostra l’elenco dei file della directory corrente.

### **Esempi di comandi Bash**

|Comando|Funzione|
|---|---|
|`pwd`|Mostra la directory corrente|
|`ls`|Elenca i file nella cartella|
|`cd`|Cambia directory|
|`mkdir nomecartella`|Crea una nuova directory|
|`rm nomefile`|Rimuove un file|
|`cp file1 file2`|Copia un file|
|`mv file1 file2`|Sposta o rinomina un file|
|`cat nomefile`|Mostra il contenuto di un file|
|`grep parola file.txt`|Cerca una parola in un file|
|`chmod 755 script.sh`|Cambia i permessi di un file|
|`./script.sh`|Esegue uno script Bash|

### **Script Bash**
Uno **script Bash** è un file di testo che contiene una sequenza di comandi.  
Serve per **automatizzare operazioni** che faresti manualmente.

Esempio:
``` bash
#!/bin/bash 
echo "Ciao, questo è uno script Bash!" 
mkdir prova 
cd prova 
touch file.txt 
echo "Ho creato un file chiamato file.txt dentro la cartella prova"
```

- La prima riga `#!/bin/bash` indica al sistema che deve usare **Bash** per eseguire il file.
- Ogni riga successiva è un comando che Bash eseguirà in sequenza.

### **Variabili e parametri**
Bash supporta le **variabili**, come nei linguaggi di programmazione:
``` bash
nome="Giovanni" 
echo "Ciao $nome"
```

→ Output: `Ciao Giovanni`

Puoi anche usare **parametri**:

``` bash
#!/bin/bash 
echo "Ciao $1"
```

Eseguendo:

`./script.sh Giovanni`

→ Output: `Ciao Giovanni`

###  **Strutture logiche e cicli**
Bash supporta **condizioni e loop**, come `if`, `for`, `while`.
### Esempio `if`:
``` bash
if [ -f "file.txt" ]; then   
	echo "Il file esiste!" 
else   
	echo "Il file non esiste!" 
fi
```

### Esempio `for`:
``` bash
for i in {1..5}; do   
	echo "Numero $i" 
done
```

### **Redirezione e pipe**
Bash permette di **reindirizzare** l’output e concatenare comandi.

| Simbolo | Significato                                 |
| ------- | ------------------------------------------- |
| `>`     | Scrive l’output su un file (sovrascrivendo) |
| `>>`    | Aggiunge l’output a un file esistente       |
| `<`     | Legge input da un file                      |
| `       | `                                           |
| \|      | Serve per concatenare due comandi           |

Esempio:
``` bash
ls | grep ".txt"
```

→ Mostra solo i file con estensione `.txt`.

### **Perché è importante imparare Bash**
- È **fondamentale nei server Linux** (che non hanno GUI).
- È usato da **programmatori, sysadmin, DevOps e data scientist**.
- Ti permette di **automatizzare** qualsiasi cosa.
- È **compatibile con Git**, Docker, Python, ecc.
- È uno strumento essenziale per chi lavora nello sviluppo software o nella gestione di sistemi.

## GUI (Graphical User Interface)

Meglio **non affidarsi alle GUI**, poiché non permettono di imparare a fondo come funziona il sistema operativo, cosa che invece la **Bash** consente.

## Comandi utili per la shell
##### Comandi base
- `xdg-open`: apre un file (es. PDF).
- `ls`: mostra i file nella cartella corrente.
    - `ls path` → mostra i file in un percorso specifico
    - `ls -f` → mostra anche i file nascosti (quelli che iniziano con `.`)
    - `ls test_*` → mostra tutti i file che iniziano per "test_"
    - `ls ?.cpp` → mostra file con un solo carattere prima di `.cpp`
    - `ls *.cpp` → mostra tutti i file che finiscono con `.cpp`
- `man` → apre il manuale di un comando (es. `man zip | grep password`)
- `cd` → cambia directory (`cd downloads`, `cd ..`, `cd ~`)
- `rm` → rimuove file o cartelle
- `mv` → sposta o rinomina un file
- `pwd` → mostra il percorso corrente
- `$PWD` → variabile che contiene lo stesso percorso
- **TAB** → autocompletamento dei comandi

## Comandi di visualizzazione
- `cat` → mostra il contenuto di un file
- `head` → mostra le prime 10 righe
- `tail` → mostra le ultime 10 righe
- `>` → sovrascrive un file
- `>>` → aggiunge del testo in coda
- `cat file1.txt | grep parola` → concatena e filtra

## Comandi rapidi

- `CTRL + C` → interrompe un comando
- `CTRL + Z` → manda un processo in background
- `CTRL + R` → cerca un comando precedente
- `CTRL + L` → pulisce il terminale
- `!!` → ripete l’ultimo comando
- `exit` → chiude la sessione
- `more` / `less` → leggono un file a blocchi

## Variabili e altri comandi utili
- `$@` → tutti i parametri
- `$1`, `$2` → primo e secondo parametro
- `wget` → scarica una pagina web
- `curl` → trasferisce dati da/verso un URL
- `zip` → crea un archivio zip
- `mysql` / `mysqldump` → comandi per database MySQL

Esempi simpatici:
- `sleep 10 && echo "Ho finito"`
- `echo "Ciao nonna" | espeak -v it` → fa parlare lo speaker
- `notify "Ho finito"` → invia una notifica di fine processo

## Esercizio base (10-20 min)
1. `mkdir first`
2. `cd first`
3. `touch person.txt`
4. `mv person.txt another.txt`
5. `cp another.txt copy.txt`
6. `rm copy.txt`
7. `cp -r first second`
8. `rm -r second`

## Alias e Git Ignore
- È possibile creare **alias personalizzati** (vedi slide).
- Il file `.gitignore` serve a ignorare file non necessari nel repository.

# Lezione 2 — GIT

## Cos’è GIT
Git è stato creato dagli sviluppatori di **Linux** per gestire le versioni del software.  
Oggi è usato ovunque per il **version control**.

### 🎓 Come impararlo
- Oh My Git
- [Learn Git in 5 minutes](https://learngitbranching.js.org/)

## Comandi principali
### 1️⃣ Configurazione iniziale

``` bash
git config --global user.name "Nome Cognome"
git config --global user.email "tuaemail@example.com"
git config --global core.editor nano
git config --list
```

### 2️⃣ Creazione e tracciamento file
- `git init` → inizializza la repo
- `git add nomefile` → aggiunge file al tracciamento
- `git commit -m "messaggio"` → salva una versione
- `git status` → mostra i file tracciati
- `git log` → storico delle modifiche

### 3️⃣ Visualizzare differenze
``` bash
git diff
git diff <id_commit>
```

### 4️⃣ Gestione file
- `git checkout nomefile` → ripristina versione precedente
- `git rm nomefile` → rimuove file e aggiorna repo
- `git mv` → sposta o rinomina file

## Branching e Versioni
- `git branch` → crea un ramo
- `git checkout` → cambia ramo
- `git merge` → unisce rami
- `git revert` → riporta un commit eliminato
- `git reset` → annulla modifiche

📚 Link utile:  
👉 [https://learngitbranching.js.org/?locale=it_IT](https://learngitbranching.js.org/?locale=it_IT)

# Lezione 3 — GitHub
## Cos’è
**GitHub** è una piattaforma cloud per gestire repository Git.  
Permette di archiviare, condividere e collaborare sul codice.

### Funzionalità
- Repository pubbliche e private
- Like, star, fork, pull request
- Collaborazione tra utenti

## Creare e pubblicare una repository

### Primo push
``` csharp
echo "# test_qd" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/tuonome/test_qd.git
git push -u origin main
```

### Aggiornare repository
``` bash
git remote add origin https://github.com/tuonome/test_qd.git
git branch -M main
git push -u origin main
```

### Clonare repository

``` bash
git clone <link_repo>
```

# Lezione 4 — Open Source
## Cos’è
Software **open-source** = codice accessibile a tutti, modificabile e ridistribuibile liberamente.

### 🔹 Microsoft e l’open source
In passato Microsoft era contraria all’open source (caso _Internet Explorer_).  
Con il tempo ha cambiato rotta:
- Ha creato **.NET open source**
- Ha acquistato **GitHub**
- Ha rilasciato **TypeScript**, **Visual Studio Code**
- Ha introdotto **WSL (Windows Subsystem for Linux)**
- Supporta Linux Foundation e Azure

### 🔹 Android
Basato su Linux, open-source, utilizzato da tutte le aziende per i dispositivi mobili.

### 🔹 BSD
Sistema operativo open-source (senza obbligo di redistribuzione del codice).  
Usato in:
1. PlayStation
2. macOS (kernel Darwin)

## Licenze Software
Le licenze definiscono come può essere usato e distribuito un software.

|Licenza|Caratteristiche|
|---|---|
|**MIT**|Base + copyright|
|**Apache 2.0**|Include changelog e condizioni d’uso|
|**GNU GPLv3**|Deve essere open-source|
|**LGPLv3**|Librerie possono restare chiuse|
|**AGPLv3**|Simile a GPL ma per software web|
## Comunità Open Source
- **manGOS** → storica community open-source
- **TrinityCore / AzerothCore** → derivate da manGOS
- **Continuous-manGOS** → nuova generazione di sviluppatori
- **LibreOffice** → fork di OpenOffice

Avere un **profilo GitHub attivo** e **LinkedIn aggiornato** aiuta molto nella carriera.

_Bounty program_: risolvi bug e vieni pagato.

## 🇮🇹 Redis
Software open-source creato dall’italiano **Salvatore Sanfilippo** (antirez).

## 🧑‍💻 UNICT Devs
Comunità di sviluppatori dell’Università di Catania.  
Progetti:
- SPOTTED DMI
- DMI NEWS
- DMI_BOT

_(Vedi slide 3 su Telegram)_

# 🐍 **Python – Introduzione**

## 💡 Cos’è Python

**Python** è un linguaggio di programmazione creato da **Guido van Rossum** e rilasciato nel **1991**.  
È oggi uno dei linguaggi più popolari al mondo, usato per:

- 🌐 **Web development** (lato server)
    
- 💻 **Software development**
    
- 🧮 **Matematica e analisi dati**
    
- ⚙️ **System scripting** e automazione
    

🔗 **Riferimento:** [StackOverflow Developer Survey 2021](https://insights.stackoverflow.com/survey/2021#most-popular-technologies-language)

---

## ⚙️ Installazione

### 🐧 Linux

`sudo apt install python`

### 🍎 macOS

`brew install python`

### 🪟 Windows

Scarica da [python.org/downloads](https://www.python.org/downloads/)

---

## 👋 Hello World

Il tuo primo programma in Python:

`print('Hello World!')`

Confronto con C++:

`#include <iostream> using namespace std;  int main() {     cout << "Hello World!" << endl;     return 0; }`

In Python basta **una riga**.  
L’output è immediato e non servono dichiarazioni o tipi espliciti.

---

# ✍️ **Stile e Indentazione**

In Python **l’indentazione** (spazi) è parte della sintassi.  
Non si usano parentesi `{}` come in C o Java.

Esempio corretto:

`if 5 > 2:     print("Five is greater than two!")`

Esempio errato (causa errore di indentazione):

`if 5 > 2: print("Five is greater than two!")  # ❌`

---

# 🔤 **Case Style e Commenti**

I commenti si scrivono con `#`.

`# Questo è un commento print("OpenSource")  # Altro commento`

Commenti multilinea:

`""" Questo è un commento su più righe. """`

---

# 🧩 **Variabili e Tipi**

Python è **dinamico**: non serve dichiarare i tipi.

`x = 4 print(type(x))  # <class 'int'>  x = "Sally" print(type(x))  # <class 'str'>`

Conversione di tipo:

`x = str(3)    # '3' y = int(3)    # 3 z = float(3)  # 3.0`

👉 **Duck Typing:** in Python conta il _comportamento_, non il tipo dichiarato.

---

# 🍊 **Assegnazione multipla e unpacking**

### Assegnare più valori:

`x, y, z = "Orange", "Banana", "Cherry" print(x, y, z)`

### Unpacking di una collezione:

`fruits = ["apple", "banana", "cherry"] x, y, z = fruits print(x, y, z)`

---

# 🌍 **Scope e Funzioni**

`x = "awesome"  def myfunc() -> None:     print("Python is " + x)  myfunc()`

Output:

`Python is awesome`

---

### Scope locale e globale

`x = "awesome"  def myfunc() -> None:     x = "fantastic"     print("Python is " + x)  myfunc() print("Python is " + x)`

Output:

`Python is fantastic Python is awesome`

---

# 🌐 **La parola chiave `global`**

Serve per modificare variabili globali dentro una funzione.

`def myfunc() -> None:     global x     x = "fantastic"  myfunc() print("Open source is " + x)`

Output:

`Open source is fantastic`

---

# 🧠 **Tipi di dati in Python**

|Categoria|Tipi|
|---|---|
|Testo|`str`|
|Numerici|`int`, `float`, `complex`|
|Sequenze|`list`, `tuple`, `range`|
|Mappature|`dict`|
|Insiemi|`set`, `frozenset`|
|Booleani|`bool`|
|Binari|`bytes`, `bytearray`, `memoryview`|

Esempio:

`x = "Hello World"              # str x = 20                         # int x = 20.5                       # float x = 1j                         # complex x = ["apple", "banana"]        # list x = ("apple", "banana")        # tuple x = range(6)                   # range x = {"name": "John"}           # dict x = {"apple", "banana"}        # set x = frozenset({"apple", "banana"})  # frozenset x = True                       # bool x = b"Hello"                   # bytes x = bytearray(5)               # bytearray x = memoryview(bytes(5))       # memoryview`

---

# 🔡 **Stringhe e array**

Le stringhe sono **sequenze indicizzate**.

`a = "Hello, World!" print(a[1])  # e`

Ciclo su stringa:

`for x in "mock":     print(x)`

Lunghezza:

`print(len("Hello World"))  # 12`

Controllo sottostringa:

`txt = "freedom" print("free" in txt)  # True`

---

# ✂️ **Slicing (Substring)**

`b = "Hello, World!" print(b[2:5])   # llo print(b[:5])    # Hello print(b[2:])    # llo, World! print(b[-5:-2]) # orl`

---

# 🔣 **Operatori principali**

`x in y       # True se x è in y x not in y x is y       # Confronta gli ID (stesso oggetto) x is not y  x and y      # AND logico x or y       # OR logico not(x < 5)   # Negazione`

---

# 🔁 **Loop e Range**

`thislist = ["apple", "linux", "microsoft"] for i in range(len(thislist)):     print(thislist[i])`

Versione compatta:

`[print(x) for x in thislist]`

---

# ⚡ **Short Loop (List Comprehension)**

Forma tradizionale:

`fruits = ["apple", "banana", "cherry"] newlist = [] for x in fruits:     if "a" in x:         newlist.append(x) print(newlist)`

Forma compatta:

`newlist = [x for x in fruits if "a" in x]`

Sintassi generale:

`newlist = [expression for item in iterable if condition]`

---

# 🧮 **Operatore ternario**

`'Identical' if x == y else 'Not identical'`

Equivalente al ternario C:

`x == y ? "identical" : "not identical"`

Ecco gli **appunti completi e ordinati su Continuous Integration / Delivery e GitHub Actions**, scritti in italiano chiaro, **con sintassi formattata per Obsidian**, emoji, blocchi YAML e spiegazioni — come quelli che ti ho già fatto per Python 👇

---

# 🚀 Continuous Integration & Delivery (CI/CD)

## 🔄 Continuous Integration (CI)

**Continuous Integration** è la pratica di integrare frequentemente il codice sviluppato dai vari membri di un team in un repository condiviso (ad esempio GitHub).  
Ogni integrazione viene verificata automaticamente tramite **build** e **test** per garantire che il codice rimanga funzionante.

✅ Obiettivi:

- Rilevare errori rapidamente
    
- Automatizzare i test
    
- Migliorare la qualità del software
    

---

## 📦 Continuous Delivery (CD)

**Continuous Delivery** è l’estensione naturale della CI.  
Si occupa di **automatizzare il rilascio** (deployment) del software dopo la fase di integrazione.

⚙️ Obiettivi:

- Rilasciare il codice in produzione in modo rapido, sicuro e ripetibile
    
- Minimizzare interventi manuali
    
- Automatizzare build, test e deploy
    

---

## 🧩 Pipeline

Una **pipeline** è l’insieme di step automatici eseguiti in sequenza (build → test → deploy).

📚 Tipicamente:

`Pipeline → CI / CD`

📦 Esempi di strumenti CI/CD:

- **GitHub Actions**
    
- **GitLab CI**
    
- **Jenkins**
    
- **CircleCI**
    

---

# ⚙️ GitHub Actions

Introdotto da **GitHub nel 2018**, permette di automatizzare direttamente dal repository le fasi di:

- Build
    
- Test
    
- Deploy
    

---

## 🧪 Esempio base – “Hello World”

📄 `.github/workflows/hello-world.yml`

`name: Hello-World  on:   push:     branches: [main]   pull_request:     branches: [main]  jobs:   hello-world-job:     runs-on: ubuntu-latest      steps:       - name: Hello World         run: echo 'Hello World'`

➡️ Questo workflow stampa “Hello World” ad ogni push o pull request sul branch `main`.

---

## 💻 Esempio – Compilazione in C++

📄 `.github/workflows/build.yml`

`name: build-hello-world  on:   push:     branches: [main]   pull_request:     branches: [main]  jobs:   build-hello-world:     runs-on: ubuntu-latest     steps:       - uses: actions/checkout@v4        - name: install g++         run: sudo apt install -y g++        - name: check build         run: |           g++ hello_world.cpp -o hello_world           ./hello_world`

➡️ Esegue automaticamente la compilazione e l’esecuzione di un file C++.

---

## 🧱 Release automatizzata

📄 `.github/workflows/release.yml`

`name: release-hello-world  on:   workflow_dispatch:  jobs:   build-hello-world:     permissions: write-all     runs-on: macos-latest     steps:       - uses: actions/checkout@v4        - name: compile and run         run: g++ hello_world.cpp -o hello_world_mac        - name: Create Release         env:           GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}         run: >           gh release create ${{ github.ref_name }}           "hello_world_mac"           --generate-notes           --title "Version ${{ github.ref_name }}"`

➡️ Questo workflow viene lanciato manualmente (`workflow_dispatch`) e crea una **release** su GitHub con un eseguibile compilato.

---

## 🌍 Release cross-platform

📄 `.github/workflows/release-matrix.yml`

`name: release-hello-world  on:   workflow_dispatch:  jobs:   create-release:     permissions: write-all     runs-on: ubuntu-latest     steps:       - uses: actions/checkout@v4       - name: Create Release         env:           GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}         run: gh release create ${{ github.ref_name }} --generate-notes --title "Version ${{ github.ref_name }}"    build-hello-world:     needs: create-release     permissions: write-all      strategy:       matrix:         include:           - os: ubuntu-latest             file_name: hello_world_linux           - os: macos-latest             file_name: hello_world_mac           - os: windows-latest             file_name: hello_world_windows.exe      runs-on: ${{ matrix.os }}     name: ${{ matrix.os }}      steps:       - uses: actions/checkout@v4       - name: compile         run: g++ hello_world.cpp -o ${{ matrix.file_name }}        - name: Create Release         env:           GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}         run: gh release upload ${{ github.ref_name }} "${{ matrix.file_name}}"`

➡️ Crea e pubblica **eseguibili multipiattaforma** (Linux, macOS, Windows).

---

## 🧩 Pipeline Checks (Esempio C++)

`name: build-hello-world  on:   push:     branches: [main]   pull_request:     branches: [main]  jobs:   build-hello-world:     runs-on: ubuntu-latest     steps:       - uses: actions/checkout@v4       - name: install g++         run: sudo apt install -y g++       - name: check build         run: |           g++ hello_world.cpp -o hello_world           ./hello_world`

### Esempio di codice:

`#include <iostream> using namespace std;  int main() {   cout << "Hello World" << endl;   return 0; }`

---

## 🧹 Linter (Cppcheck)

`name: build-hello-world  on:   push:     branches: [main]   pull_request:     branches: [main]  jobs:   build-hello-world:     runs-on: ubuntu-latest     steps:       - uses: actions/checkout@v4       - name: install g++         run: sudo apt install -y g++ cppcheck       - name: run cppcheck         run: |           cppcheck hello_world.cpp --output-file=report.txt           if [ -s report.txt ]; then             cat report.txt             exit 1           fi       - name: check build         run: |           g++ hello_world.cpp -o hello_world           ./hello_world`

➡️ Analizza il codice con **Cppcheck** e fallisce se vengono trovati errori statici.

---

## 🧠 Python – Pylint & Pytest

`name: CI  on:   push:     branches: [main]     paths-ignore:       - "README.md"       - "docs/**"   pull_request:     branches: [main]     paths-ignore:       - "README.md"       - "docs/**"  jobs:   test:     runs-on: ubuntu-latest      steps:       - uses: actions/checkout@v2        - name: Set up Python 3.10.0         uses: actions/setup-python@v2         with:           python-version: 3.10.0        - name: Install dependencies         run: |           python -m pip install --upgrade pip           if [ -f requirements.txt ]; then pip install -r requirements.txt; fi           if [ -f requirements_dev.txt ]; then pip install -r requirements_dev.txt; fi        - name: Lint with pylint         run: pylint src        - name: Test with pytest         run: pytest --cov src tests/ --cov-fail-under=75`

➡️ Automatizza:

- L’intallazione delle dipendenze
    
- L’analisi del codice (`pylint`)
    
- I test unitari (`pytest`)
    

---

## 🐳 Reusable Workflows – Docker Image

Workflow riutilizzabile per creare e pubblicare immagini Docker.

📄 `.github/workflows/docker.yml`

`name: Create and publish a Docker image  on:   workflow_call:     inputs:       repo_ref:         required: true         type: string  env:   REGISTRY: ghcr.io   IMAGE_NAME: ${{ inputs.repo_ref }}  jobs:   build-and-push-image:     runs-on: ubuntu-latest     permissions:       contents: read       packages: write      steps:       - name: Checkout repository         uses: actions/checkout@v2        - name: Log in to the Container registry         uses: docker/login-action@f054a8b539a109f9f41c372932f1ae047eff08c9         with:           registry: ${{ env.REGISTRY }}           username: ${{ github.actor }}           password: ${{ secrets.GITHUB_TOKEN }}        - name: Extract metadata         id: meta         uses: docker/metadata-action@98669ae865ea3cffbcbaa878cf57c20bbf1c6c38         with:           images: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}        - name: Build and push Docker image         uses: docker/build-push-action@ad44023a93711e3deb337508980b4b5e9bcdc5dc         with:           context: .           push: true           tags: ${{ steps.meta.outputs.tags }}           labels: ${{ steps.meta.outputs.labels }}`

📎 Esempio di uso:

`name: Create and publish Docker image  on:   push:     branches: ['main']  jobs:   build:     uses: unict-dmi/reusable-workflows/.github/workflows/docker.yml@main     with:       repo_ref: ${{ github.repository }}`

---

## 🔐 Secrets & Token (Telegram)

Esempio di utilizzo di **GitHub Secrets** per inviare un messaggio Telegram.

`name: Telegram-Secret-Token  on:   push:     branches: [main]   pull_request:     branches: [main]  jobs:   hello-world-job:     runs-on: ubuntu-latest     steps:       - name: Telegram Notify         run: >           curl -s --data-urlencode "text=Hello World"           "https://api.telegram.org/bot${{ secrets.MY_SECRET_TOKEN }}/sendMessage?chat_id=104400"`

➡️ Usa una **variabile segreta (`MY_SECRET_TOKEN`)** per accedere in sicurezza all’API di Telegram.

---

## 🌐 GitHub Pages

GitHub Pages permette di **pubblicare siti statici** direttamente da un repository.  
Può essere integrato nella pipeline CI/CD per l’**aggiornamento automatico** del sito ad ogni push.

# 🧱 Principi SOLID e Clean Code

## 🔹 Introduzione

I principi **SOLID** rappresentano le basi della buona progettazione orientata agli oggetti.  
Sono cinque regole che aiutano a scrivere codice **più chiaro, mantenibile e riutilizzabile**.

---

## 🧩 **S — Single Responsibility Principle (SRP)**

> “Una classe dovrebbe avere una sola e unica ragione per esistere.”

Ogni classe o funzione dovrebbe **avere una singola responsabilità**.  
Un modulo che fa troppe cose diventa difficile da mantenere o estendere.

### ❌ Bad code

`import numpy as np  def math_operations(list_):     # Calcola la media     print(f"The mean is {np.mean(list_)}")      # Calcola il massimo     print(f"The max is {np.max(list_)}")  math_operations([1, 2, 3, 4, 5])`

👉 Qui la funzione ha **due responsabilità**: calcola sia la media che il massimo.

---

### ✅ Good code

`import numpy as np  def get_mean(list_: list[int]) -> None:     print(f"The mean is {np.mean(list_)}")  def get_max(list_: list[int]) -> None:     print(f"The max is {np.max(list_)}")  def main(list_: list[int]) -> None:     get_mean(list_)     get_max(list_)  main([1, 2, 3, 4, 5])`

➡️ Ogni funzione ha **una sola responsabilità**, più facile da testare e modificare.

---

## 🔹 **O — Open/Closed Principle (OCP)**

> “Le entità software dovrebbero essere aperte all’estensione, ma chiuse alla modifica.”

Il codice dovrebbe permettere **nuove funzionalità senza modificare quello esistente**.

### ❌ Bad code

`class Animal:     def __init__(self, name: str):         self.name = name  animals = [     Animal('lion'),     Animal('mouse') ]  def animal_sound(animals: list):     for animal in animals:         if animal.name == 'lion':             print('roar')         elif animal.name == 'mouse':             print('squeak')`

➡️ Se volessimo aggiungere un nuovo animale, dovremmo **modificare la funzione**.

---

### ✅ Good code

`class Animal:     def __init__(self, name: str):         self.name = name      def make_sound(self) -> None:         pass  class Lion(Animal):     def make_sound(self) -> str:         return 'roar'  class Mouse(Animal):     def make_sound(self) -> str:         return 'squeak'  def animal_sound(animals: list) -> None:     for animal in animals:         print(animal.make_sound())  animals = [Lion('Simba'), Mouse('Jerry')] animal_sound(animals)`

➡️ Ora basta **aggiungere una nuova classe** per estendere il comportamento.

---

## 🔹 **L — Liskov Substitution Principle (LSP)**

> “Le classi derivate devono poter sostituire le classi base senza rompere il codice.”

### ❌ Bad code

`from abc import ABC, abstractmethod  class Notification(ABC):     @abstractmethod     def notify(self, message, email):         pass  class Email(Notification):     def notify(self, message, email):         print(f'Send {message} to {email}')  class SMS(Notification):     def notify(self, message, phone):         print(f'Send {message} to {phone}')  notification = SMS() notification.notify('Hello', 'john@test.com')`

➡️ Gli argomenti cambiano da una sottoclasse all’altra → violazione del principio.

---

### ✅ Good code

`from abc import ABC, abstractmethod  class Notification(ABC):     @abstractmethod     def notify(self, message: str) -> None:         pass  class Email(Notification):     def __init__(self, email: str):         self.email = email      def notify(self, message: str) -> None:         print(f'Send "{message}" to {self.email}')  class SMS(Notification):     def __init__(self, phone: str):         self.phone = phone      def notify(self, message: str) -> None:         print(f'Send "{message}" to {self.phone}')  notification = Email('stefano.borzi@phd.unict.it') notification.notify('Hello')`

➡️ Tutte le classi derivate implementano lo stesso metodo `notify`.

---

## 🔹 **I — Interface Segregation Principle (ISP)**

> “Molte interfacce specifiche sono meglio di una interfaccia generica.”

Ogni classe dovrebbe **implementare solo i metodi di cui ha bisogno**.

### ❌ Bad code

`from abc import ABC, abstractmethod  class Mammals(ABC):     @abstractmethod     def swim():         print("Can Swim")      @abstractmethod     def walk():         print("Can Walk")  class Whale(Mammals):     def swim():         print("Whales can swim")  Human.walk()   # Humans can walk Whale.walk()   # ❌ Non tutti i mammiferi camminano`

---

### ✅ Good code

`from abc import ABC, abstractmethod  class Walker(ABC):     @abstractmethod     def walk() -> None:         pass  class Swimmer(ABC):     @abstractmethod     def swim() -> None:         pass  class Human(Walker, Swimmer):     def walk() -> None:         print("Humans can walk")     def swim() -> None:         print("Humans can swim")  class Whale(Swimmer):     def swim() -> None:         print("Whales can swim")  Human.walk() Human.swim() Whale.swim()`

➡️ Ogni classe implementa **solo l’interfaccia necessaria**.

---

## 🔹 **D — Dependency Inversion Principle (DIP)**

> “Le astrazioni non devono dipendere dai dettagli, ma i dettagli devono dipendere dalle astrazioni.”

### ❌ Bad code

`class FXConverter:     def convert(self, from_curr, to_curr, amount):         print(f'{amount} {from_curr} = {amount * 1.2} {to_curr}')         return amount * 1.2  class App:     def start(self):         converter = FXConverter()         converter.convert('EUR', 'USD', 100)  app = App() app.start()`

➡️ L’app dipende direttamente da una classe concreta.

---

### ✅ Good code

`from abc import ABC  class CurrencyConverter(ABC):     def convert(self, from_curr: str, to_curr: str, amount: float) -> float:         pass  class FXConverter(CurrencyConverter):     def convert(self, from_curr: str, to_curr: str, amount: float) -> float:         print('Converting currency using FX API')         print(f'{amount} {from_curr} = {amount * 1.2} {to_curr}')         return amount * 1.2  class App:     def __init__(self, converter: CurrencyConverter):         self.converter = converter      def start(self):         self.converter.convert('EUR', 'USD', 100)  converter = FXConverter() app = App(converter) app.start()`

➡️ L’app dipende da un’**interfaccia astratta**, non da una classe concreta.

---

# 💡 Principi di Code Quality

## 🧠 DRY — _Don’t Repeat Yourself_

Evita la duplicazione del codice.

### ❌ Bad code

`text1 = 1 text2 = 2 text3 = 3 print(f"Number: {text1}") print(f"Number: {text2}") print(f"Number: {text3}")`

### ✅ Good code

`texts = [1, 2, 3] for t in texts:     print(f"Number: {t}")`

---

## 🧩 KISS — _Keep It Simple, Stupid_

Mantieni il codice semplice.

### ❌ Bad code

`f = lambda x: 1 if x <= 1 else x * f(x - 1)`

### ✅ Good code

`def factorial(number: int) -> int:     if number <= 1:         return 1     return number * factorial(number - 1)`

---

## 🔀 SoC — _Separation of Concerns_

Ogni file o modulo deve avere un compito specifico.

### ❌ Bad code

`# calculator.py class Calculator():     def sum(num1, num2):         return num1 + num2      def convert_to_float(num):         return float(num)`

### ✅ Good code

`# calculator.py class Calculator():     def sum(num1, num2):         return num1 + num2  # helpers.py def convert_to_float(num):     return float(num)`

---

# ✨ Clean Code — Buone pratiche

## 📛 Usa nomi chiari e descrittivi

`# ❌ Bad c = 5 d = 12  # ✅ Good city_counter = 5 elapsed_time_in_days = 12`

---

## 🔠 Evita abbreviazioni ambigue

`# ❌ Bad fna = 'Bob'  # ✅ Good first_name = 'Bob'`

---

## 🧱 Evita numeri magici

`# ❌ Bad def roll():     return random.randint(0, 36)  # ✅ Good ROULETTE_POCKET_COUNT = 36 def roll():     return random.randint(0, ROULETTE_POCKET_COUNT)`

---

## ⚙️ Evita flag eccessive

`# ❌ Bad def transform(text, uppercase):     if uppercase:         return text.upper()     return text.lower()  # ✅ Good def uppercase(text): return text.upper() def lowercase(text): return text.lower()`

---

## 🧱 Crea classi per strutture complesse

`# ✅ Good class BlogPost:     def __init__(self, title, author, created_timestamp, content):         self.title = title         self.author = author         self.created_timestamp = created_timestamp         self.content = content`

# Comandi Linux (Riepilogo)
1. `ls` → lista file e cartelle
2. `mv` → sposta o rinomina file
3. `ssh` → connessione remota
4. `cd` → cambia directory
5. `cat` → mostra contenuto
6. `sudo` → comandi come admin
7. `pwd` → mostra percorso
8. `grep` → cerca pattern in file
9. `top` → mostra processi attivi
10. `mkdir` → crea directory
11. `find` → trova file
12. `wget` → scarica file web
13. `rm` → rimuove file
14. `chmod` → cambia permessi
15. `tar` → crea archivi
16. `cp` → copia file
17. `chown` → cambia proprietario
18. `gzip` → comprime file
