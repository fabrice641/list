Esercizio che puoi svolgere con HTML, CSS, JavaScript e Bootstrap 5.3.3 utilizzando Visual Studio Code:

Creazione di un'applicazione To-Do List

Obiettivo: Realizzare una semplice applicazione To-Do List che consente agli utenti di aggiungere, visualizzare e rimuovere attività. Utilizzerai HTML, CSS, JavaScript e Bootstrap 5.3.3.

 Passaggi:

1. Configurazione del progetto:
    - Crea una nuova cartella di progetto e aprila in Visual Studio Code.
    - Crea un file `index.php` per il tuo HTML.
    - Crea un file `style.css` per i tuoi stili CSS personalizzati.
    - Crea un file `index.js` per il tuo codice JavaScript.

2. Importa Bootstrap 5.3.3:
    - Aggiungi un link al file CSS di Bootstrap 5.3.3 nell'elemento `<head>` di `index.html`.
    - Aggiungi un link al file JavaScript di Bootstrap 5.3.3 all'interno dell'elemento `<body>`.

3. Layout HTML:
    - Crea un layout di base con Bootstrap 5.3.3 per l'applicazione.
    - Include un `header` per il titolo dell'applicazione.
    - Aggiungi un `input` per inserire nuove attività e un pulsante per aggiungerle alla lista.
    - Crea una `ul` (lista non ordinata) per visualizzare le attività.
    - Assicurati che il tutto sia ben stilizzato utilizzando classi Bootstrap.

4. Stile CSS:
    - Personalizza gli stili di `index.html` nel file `style.css`.
    - Applica stili alle varie sezioni della pagina, come il `header`, l'`input` e la lista.
    - Sperimenta con colori, dimensioni del carattere e layout.

5. Funzionalità JavaScript:
    - In `index.js`, implementa la logica per aggiungere nuove attività alla lista.
    - Consenti agli utenti di rimuovere le attività cliccando su un pulsante accanto a ciascuna attività.
    - Aggiorna la lista in tempo reale quando un'attività viene aggiunta o rimossa.
    - Usa la manipolazione DOM per gestire l'aggiunta e la rimozione degli elementi della lista.
    - Sperimenta con eventi come `click` e `submit`.

6. Test e ottimizzazione:
    - Testa la tua applicazione per assicurarti che funzioni correttamente.
    - Aggiungi eventuali miglioramenti e ottimizzazioni.

7. Documentazione:
    - Aggiungi commenti al tuo codice per spiegare le sezioni più importanti.
    - Scrivi una breve spiegazione delle funzionalità dell'applicazione.


Passaggi:

1. Installazione di MySQL e PhpMyAdmin:
    - Assicurati di avere MySQL installato sul tuo sistema.
    - Installa PhpMyAdmin per gestire il database con un'interfaccia web.

2. Creazione del database:
    - Accedi a PhpMyAdmin.
    - Crea un nuovo database per la tua applicazione To-Do List, ad esempio chiamato `todo_db`.
    - All'interno di `todo_db`, crea una tabella `tasks` con le seguenti colonne:
        - `id` (chiave primaria, auto-incremento, tipo `INT`).
        - `task` (tipo `VARCHAR` per memorizzare le attività).
        - `completed` (tipo `BOOLEAN` per indicare se l'attività è completata).

3. Connessione al database con PHP:
    - In `script.js`, fai una richiesta AJAX per comunicare con un file PHP che si connette al database.
    - Crea un file `database.php` per gestire la connessione al database. Includi le seguenti informazioni:
        - `hostname`: indirizzo del server MySQL (ad esempio, `localhost`).
        - `username`: il nome utente del database.
        - `password`: la password dell'utente.
        - `database`: il nome del database (`todo_db`).
    - Usa `mysqli` per stabilire la connessione al database in `database.php`.

4. Interazione con il database:
    - Crea un file PHP separato per le operazioni di inserimento e rimozione delle attività nel database (`add_task.php`, `remove_task.php`, ad esempio).
    - `add_task.php`: riceve i dati dell'attività tramite POST e inserisce la nuova attività nella tabella `tasks`.
    - `remove_task.php`: riceve l'ID dell'attività da rimuovere tramite POST e la elimina dalla tabella `tasks`.
    - Utilizza queste pagine PHP come endpoint per le richieste AJAX.

5. Aggiornamento dell'applicazione:
    - Modifica il file `script.js` per interagire con le pagine PHP create.
    - Aggiungi funzioni JavaScript per inviare richieste POST a `add_task.php` e `remove_task.php` per aggiungere o rimuovere attività.
    - Dopo aver aggiunto o rimosso un'attività, aggiorna la lista delle attività visualizzate richiedendo le informazioni dal database tramite AJAX.

6. Test e ottimizzazione:
    - Testa l'applicazione per assicurarti che le operazioni di inserimento e rimozione funzionino correttamente.
    - Assicurati che le funzionalità JavaScript interagiscano correttamente con le pagine PHP. 
