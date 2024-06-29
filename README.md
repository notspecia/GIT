## Author Details
* Name: Gabriele Speciale 
* Contact: gabriele.speciale@edu.itspiemonte.it

<br><br>

# GIT NOTES 

## 01. Configurazione degli snapshots e della GIT staging area

* ***git init*** → per creare il repository git, ha una serie di opzioni non troppo utili, tra queste ne abbiamo 2:
1. ***git init*** "nome cartella"

2. ***--initial-branch***
al suo interno c'è il file git config

<br><br>

* ***git clone [`url`]*** → utilizzato per creare una copia locale di un repository remoto presente ad esempio su GitHub o GitLab ...

<br>

* ***git config user.name `prova`*** → è il comando per modificare il nome del git config del mio progetto

<br>

* ***git config --global user.name `prova`*** → il nome utente andrà applicato a tutti i progetti

<br>

* ***code README.md*** → creato il file e lo andiamo a modificare tramite (in questo caso) VisualStudioCode

<br>

* ***git status*** → lo stato dei nostri file, vedere se tutto è andato correttamente e non ci sono problemi 

<br>

* ***git add*** → è utilizzato per aggiungere modifiche all'area di staging (farlo quando vengono effettuate delle modifiche al file)

<br>

* ***git commit -m [`messaggio descrittivo`]*** → modo più semplice per fare i commit sui file

<br>

* ***git commit --amend*** → viene utilizzato per modificare l'ultimo commit effettuato, permette di aggiungere nuove modifiche, cambiare il messaggio del commit o correggere errori senza creare un nuovo commit
effettuato questo comando, ci aprirà tramite code il nostro commit precedente che può essere modificato

<br><br>

## 02. Comandi per la gestione dei files

* ***git restore --staged `README.md`*** → viene utilizzato per rimuovere il file README.md dall'area di staging. Questo significa che le modifiche apportate al file README.md non saranno più incluse nel prossimo commit. Tuttavia, le modifiche rimarranno nel file nella directory di lavoro.

<br>

* ***rm `README.md`*** → comando per rimuovere il file, se facciamo git status git verdrà che il file è stato eliminato, VA AGGIUNTA ANCHE UNA RIMOZIONE TRAMITE -> git add README.md

<br>

* ***git rm*** → fa sia il remove + che l'add delle modifiche apportate al file, è molto + comodo del precedente

<br>

* ***git mv `README.md` `destinazione directory`*** → abbiamo spostato il file all'interno di un altra repository, anche in questo caso git si accorge e va addato e commitato questo spostament

<br>

* ***code .gitignore*** → ogni tanto possiamo avere all'interno del nostro progetto dei file che non vogliamo committare, questo file ci permette di indicare un elenco di quali files ignorare:

1. ***.txt*** → qualsiasi file che abbiamo qualunque nome che abbia come estensione txt, verranno ignorati

2. ***!"nome file".txt*** → in questo caso con il "! not ", quel file anche se ha un estensione .txt che teoricamente verrebbe ignorato, quel file potrà essere committato e visualizzato 

<br><br>

## 03. Gestione e visualizzazione della storia

* ***git log*** → con log possiamo vedere la cronologia dei commit di una repository, ogni commit possiede ognuno un ID univoco (lungo 40 caratteri)
generalmente sono fondamentali sono i primi 9 caratteri per riconoscere un commit

tra le opzioni più importanti del **git log**:
1. ***git log --oneline*** → mostra la cronologia dei commit in un formato compatto, l'hash del commit e il messaggio di commit con una sola riga

2. ***git log --all*** → mostra la cronologia dei commit di tutti i branch e non solo del branch corrente

<br> <br>

* ***git show*** → possiamo vedere i dettagli di un commit specifico, inclusi le modifiche apportate, il messaggio di commit e i metadati (ex: nome dell'autore la data...) andando ad indicare il suo ID di origine
se avviamo il comando senza aver specificato un ID, andrà a prendere l'ultimo commit effettuato

<br> <br>

* ***git diff*** → è il modo più potente tra i vari modi di vedere l'history, permette di confrontare file e commit in diversi stati non ancora aggiunti all'area di staging

<br>

* ***git diff `commit1` `commit2`*** → confronta le differenze tra due commit specificati, mettendo il loro ID univoco

<br><br>

## 04. Comandi per tornare indietro a uno stato precedente

* ***git reset*** → viene usato per spostare il puntatore del branch corrente (ex: main) a un commit specifico, (ex: feat) modificando la cronologia

<br>

* ***git revert*** → crea un nuovo commit che applica l'inverso delle modifiche apportate dal commit specificato (se una cosa è stata aggiunta, la elimina e viceversa...)

<br>

* ***git restore*** → usato per ripristinare i file dall'indice o da un commit specifico

<br>

* ***git restore --staged `file`*** → è utilizzato per rimuovere le modifiche di un file dall'area di staging, mantenendo le modifiche nella working directory

<br>

* ***git restore --staged `directory`*** → è utilizzato rimuove TUTTI i file modificati nella directory specificata dall'area di staging, mantenendo le modifiche nella working directory.

<br>

* ***git stash*** → prende e salva le ultime modifiche nella cartella corrente e nella staging non ancora committate

<br>

* ***git stash pop*** → applica le modifiche dell'ultimo stash e rimuove lo stash dalla lista

<br>

* ***git stash drop*** → scarta le modifiche dell'ultimo stash

<br><br>

## 05. Comandi per la gestione dei branch

* ***git branch*** → visualizza un elenco di tutti i branch locali

<br>

* ***git branch `nome-branch`*** → crea un nuovo branch con il nome specificato dopo il comando, ma una volta creato, non passerà immediatamente a quel branch.<br>
tra i comandi più importanti nel `branch` sono:

<br>

* ***git branch -a*** → visualizza un elenco di tutti i branch locali e anche branch remoti

<br>

* ***git branch -m `nuovo-nome`*** → permette di rinominare il branch corrente in cui ci trova

<br>

* ***git branch -d `nome-branch`*** → permette di eliminare il branch di specificato

<br><br>

* ***git checkout `nome-branch`*** →  permette di spostarsi tra i branch creati, molto utile questa operazione per selezionare la linea di sviluppo su cui lavorare (main, feature)

<br>

* ***git checkout -b `nome-branch`*** → permette la creazione di un nuovo branch, e di passare successivamente alla creazione ad esso

<br><br>

* ***git merge `nome-branch`*** → è usato per unire le modifiche applicate da un branch, in un altro branch.<br>
viene spesso utilizzato per unire un branch di funzionalità una volta che sarà completato (feature), nel branch principale quello che poi verrà pubblicato sul nostro GitHub (main / master)

<br>

* ***git merge --abort*** → utile in caso ci sia sia sbagliati a fare un merge ancora in corso, lo annulla e riporta lo stato del repository a prima dell'inizio del merge

<br> <br>


## 06. Condividere e aggiornare le repository

* ***git remote add [`repository remoto`] [`url della repository`]*** → utilizzato per aggiungere un repository remoto al tuo repository di Git locale

<br>

* ***git push -u origin [`nome branch`]*** → è utilizzato per inviare il branch locale specificato al repository remoto, e impostare il branch di tracciamento per facilitare i futuri push e pull

<br>

* ***git pull origin [`nome branch`]*** → utilizzato per recuperare e unire le modifiche dai repository remoti nel tuo branch locale

<br>

* ***git fetch*** → recupera le modifiche dal repository remoto e le unisce nel branch locale corrente
