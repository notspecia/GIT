# GIT NOTES!

## Author Details
* **Name:** Gabriele Speciale
* **Contact:** gabriele.speciale@edu.itspiemonte.it

---
<br> <br> <br> <br>

## 01. configurazione degli snapshots e della GIT staging area

questa sezione copre i comandi di base per configurare un repository Git, creare snapshot dei file e gestire l'area di staging

<br>

* **`git init`** → crea un nuovo repository Git nella directory corrente. Opzioni utili:

  1. **`git init "nome cartella"`** → crea un repository Git nella cartella specificata
  
  2. **`--initial-branch`** → specifica il nome del branch iniziale

<br> <br>


* **`git clone [url]`** → crea una copia locale di un repository remoto (ad esempio, da GitHub o GitLab)

<br>

* **`git config user.name "prova"`** → imposta il nome utente per il progetto corrente

<br>

* **`git config --global user.name "prova"`** → imposta il nome utente globalmente per tutti i progetti Git

<br>

* **`code README.md`** → crea e modifica il file README.md con Visual Studio Code

<br>

* **`git status`** → mostra lo stato dei file nel repository, verificando eventuali problemi

<br>

* **`git add [file]`** → aggiunge le modifiche di un file all'area di staging

<br>

* **`git commit -m "messaggio descrittivo"`** → effettua un commit delle modifiche con un messaggio descrittivo

<br>

* **`git commit --amend`** → modifica l'ultimo commit effettuato, permettendo di aggiungere nuove modifiche o cambiare il messaggio del commit senza crearne uno nuovo

---
<br><br>

## 02. comandi per la gestione dei files

questa sezione descrive i comandi per gestire i file nel repository Git, inclusi il ripristino, la rimozione e lo spostamento di file

<br>

* **`git restore --staged README.md`** → rimuove il file README.md dall'area di staging, mantenendo le modifiche nella directory di lavoro

<br>

* **`rm README.md`** → rimuove il file README.md. dopo questo comando, bisogna usare **`git add README.md`** per registrare la rimozione

<br>

* **`git rm`** → rimuove un file e aggiunge automaticamente la modifica all'area di staging

<br>

* **`git mv README.md destinazione_directory`** → sposta il file in un'altra directory. questo spostamento deve essere aggiunto e committato

<br>

* **`code .gitignore`** → crea o modifica il file .gitignore per specificare i file che Git deve ignorare:

  1. **`*.txt`** → ignora qualsiasi file con estensione .txt

  2. **`!"nome file".txt`** → include un file specifico con estensione .txt, anche se tutti gli altri .txt sono ignorati

---
<br> <br>

## 03. gestione e visualizzazione della storia

questa sezione copre i comandi per visualizzare e gestire la cronologia dei commit nel repository Git

<br>

* **`git log`** → mostra la cronologia dei commit di un repository, con ogni commit identificato da un ID univoco (di 40 caratteri). le opzioni principali includono:

  1. **`git log --oneline`** → mostra la cronologia dei commit in un formato compatto

  2. **`git log --all`** → mostra la cronologia dei commit di tutti i branch

<br> <br>

* **`git show`** → mostra i dettagli di un commit specifico, inclusi le modifiche apportate, il messaggio di commit e i metadati. se usato senza specificare un ID, mostra l'ultimo commit

<br>

* **`git diff`** → confronta i file e i commit in diversi stati non ancora aggiunti all'area di staging

  1. **`git diff [commit1] [commit2]`** → confronta le differenze tra due commit specificati tramite il loro ID univoco

---
<br> <br>

## 04. comandi per tornare indietro a uno stato precedente

questa sezione descrive i comandi per ripristinare il repository Git a uno stato precedente, annullando modifiche indesiderate

<br>

* **`git reset`** → sposta il puntatore del branch corrente a un commit specifico, modificando la cronologia

<br>

* **`git revert`** → crea un nuovo commit che annulla le modifiche apportate da un commit specifico

<br>

* **`git restore`** → ripristina i file dall'indice o da un commit specifico

  1. **`git restore --staged [file]`** → rimuove le modifiche di un file dall'area di staging, mantenendo le modifiche nella working directory

  2. **`git restore --staged [directory]`** → rimuove tutti i file modificati nella directory specificata dall'area di staging, mantenendo le modifiche nella working directory

<br> <br>

* **`git stash`** → salva temporaneamente le modifiche non ancora committate

  1. **`git stash pop`** → applica le modifiche dell'ultimo stash e rimuove lo stash dalla lista
  
  2. **`git stash drop`** → scarta le modifiche dell'ultimo stash

---
<br> <br>

## 05. comandi per la gestione dei branch

questa sezione copre i comandi per creare, gestire e navigare tra i branch nel repository Git

<br>

* **`git branch`** → visualizza un elenco di tutti i branch locali

  1. **`git branch [nome-branch]`** → crea un nuovo branch con il nome specificato

  2. **`git branch -a`** → visualizza un elenco di tutti i branch locali e remoti

  3. **`git branch -m [nuovo-nome]`** → rinomina il branch corrente
  
  4. **`git branch -d [nome-branch]`** → elimina il branch specificato

<br> <br>

* **`git checkout [nome-branch]`** → permette di spostarsi tra i branch creati

  1. **`git checkout -b [nome-branch]`** → crea un nuovo branch e passa immediatamente ad esso

<br> <br>

* **`git merge [nome-branch]`** → unisce le modifiche da un branch in un altro branch

  1. **`git merge --abort`** → annulla un merge in corso e ripristina lo stato del repository a prima dell'inizio del merge

---
<br> <br>

## 06. condividere e aggiornare le repository

questa sezione descrive i comandi per condividere e aggiornare il repository Git locale con un repository remoto

<br>

* **`git remote add [nome-remote] [url-del-remote]`** → aggiunge un repository remoto al tuo repository Git locale

<br>

* **`git remote -v`** → mostra l'elenco dei repository remoti associati alla repository locale

<br>

* **`git push -u origin [nome-branch]`** → invia il branch locale specificato al repository remoto e imposta il branch di tracciamento per facilitare i futuri push e pull

<br>

* **`git pull origin [nome-branch]`** → recupera e unisce le modifiche dal repository remoto nel tuo branch locale

<br>

* **`git fetch`** → recupera le modifiche dal repository remoto senza unirle automaticamente nel branch locale corrente

---
