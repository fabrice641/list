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

Creare un'applicazione To-Do List con HTML, CSS, JavaScript e Bootstrap 5.3.3 è un progetto divertente e educativo. Qui di seguito ti guiderò passo per passo nella creazione di un'applicazione To-Do List semplice e funzionale.

Passaggi:

1. Configurazione del progetto:
    - Crea una nuova cartella di progetto e aprila in Visual Studio Code.
    - All'interno della cartella, crea tre file: `index.php`, `style.css`, e `index.js`.

2. Importa Bootstrap 5.3.3:
    - Aggiungi un link al file CSS di Bootstrap 5.3.3 nell'elemento `<head>` di `index.html`:

        ```html
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
        ```

    - Aggiungi un link al file JavaScript di Bootstrap 5.3.3 all'interno dell'elemento `<body>`:

        ```html
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
        ```

3. Layout HTML:
    - Crea il layout di base nel file `index.php`:

        ```html
        <!DOCTYPE html>
        <html lang="it">

        <head>
            <meta charset="UTF-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>To-Do List</title>
            <link rel="stylesheet" href="style.css">
            <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
        </head>

        <body>
            <div class="container">
                <header class="my-4">
                    <h1 class="text-center">To-Do List</h1>
                </header>
                <div class="input-group mb-3">
                    <input type="text" id="task-input" class="form-control" placeholder="Aggiungi un'attività">
                    <button class="btn btn-primary" id="add-task">Aggiungi</button>
                </div>
                <ul class="list-group" id="task-list">
                    <!-- Le attività verranno inserite qui -->
                </ul>
            </div>

            <script src="index.js"></script>
            <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
        </body>

        </html>
        ```

4. Stile CSS:
    - Personalizza gli stili CSS nel file `style.css`:

        ```css
        /* style.css */
        body {
            padding-top: 20px;
        }

        .input-group {
            margin-bottom: 20px;
        }

        ul.list-group li {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        ```

5. Funzionalità JavaScript:
    - Scrivi il codice JavaScript per aggiungere e rimuovere attività in `index.js`:

        ```javascript
        // index.js
        document.addEventListener('DOMContentLoaded', function () {
            const taskInput = document.getElementById('task-input');
            const addTaskButton = document.getElementById('add-task');
            const taskList = document.getElementById('task-list');

            function addTask() {
                const taskText = taskInput.value.trim();
                if (taskText) {
                    const listItem = document.createElement('li');
                    listItem.className = 'list-group-item d-flex justify-content-between';
                    listItem.innerHTML = `
                        <span>${taskText}</span>
                        <button class="btn btn-danger btn-sm remove-task">Rimuovi</button>
                    `;
                    taskList.appendChild(listItem);
                    taskInput.value = '';
                }
            }

            function removeTask(event) {
                const button = event.target;
                if (button.classList.contains('remove-task')) {
                    const listItem = button.parentElement;
                    taskList.removeChild(listItem);
                }
            }

            addTaskButton.addEventListener('click', addTask);
            taskList.addEventListener('click', removeTask);
        });
        ```

6. Test e ottimizzazione:
    - Testa la tua applicazione per assicurarti che funzioni correttamente.
    - Aggiungi eventuali miglioramenti e ottimizzazioni come ad esempio funzionalità di ordinamento o marcatura delle attività completate.

7. Documentazione:
    - Aggiungi commenti al tuo codice per spiegare le sezioni più importanti.
    - Scrivi una breve spiegazione delle funzionalità dell'applicazione.

Ora hai una semplice applicazione To-Do List funzionante! Puoi personalizzare ulteriormente l'aspetto e le funzionalità in base alle tue esigenze.
    - Testa l'applicazione per assicurarti che le operazioni di inserimento e rimozione funzionino correttamente.
    - Assicurati che le funzionalità JavaScript interagiscano correttamente con le pagine PHP.


    Poiché l'applicazione To-Do List non richiede interazioni con il database in base alla tua richiesta originale, il codice PHP non era necessario. Tuttavia, se vuoi aggiungere funzionalità avanzate come la persistenza dei dati in un database o la gestione degli utenti, il PHP sarà necessario per comunicare con il database e gestire le richieste.

Esempio di un'applicazione To-Do List con PHP

 1. Database
Assicurati di avere un database MySQL configurato con una tabella `tasks` per memorizzare le attività. Puoi creare la tabella con questa query:

```sql
CREATE TABLE tasks (
    id INT AUTO_INCREMENT PRIMARY KEY,
    task VARCHAR(255) NOT NULL,
    completed BOOLEAN DEFAULT FALSE
);
```

2. Configurazione della connessione al database
Crea un file `database.php` per gestire la connessione al database. Includi le seguenti informazioni:

```php
<?php
$hostname = 'localhost';
$username = 'root'; // Cambia con il tuo nome utente del database
$password = ''; // Cambia con la tua password del database
$database = 'todo_db';

$conn = new mysqli($hostname, $username, $password, $database);

if ($conn->connect_error) {
    die("Connessione al database fallita: " . $conn->connect_error);
}
?>
```

3. Inserimento di nuove attività
Crea un file `add_task.php` per inserire nuove attività nella tabella `tasks`:

```php
<?php
include 'database.php';

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $task = $_POST['task'];

    $sql = "INSERT INTO tasks (task) VALUES (?)";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param('s', $task);
    
    if ($stmt->execute()) {
        echo "Attività aggiunta con successo!";
    } else {
        echo "Errore nell'aggiungere attività: " . $stmt->error;
    }

    $stmt->close();
}

$conn->close();
?>
```

 4. Rimozione di attività
Crea un file `remove_task.php` per rimuovere attività dalla tabella `tasks`:

```php
<?php
include 'database.php';

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $id = $_POST['id'];

    $sql = "DELETE FROM tasks WHERE id = ?";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param('i', $id);
    
    if ($stmt->execute()) {
        echo "Attività rimossa con successo!";
    } else {
        echo "Errore nella rimozione dell'attività: " . $stmt->error;
    }

    $stmt->close();
}

$conn->close();
?>
```

5. Interazione con il database
Nel file `index.js`, aggiungi il codice JavaScript per inviare richieste POST a `add_task.php` e `remove_task.php`:

```javascript
// index.js
document.addEventListener('DOMContentLoaded', function () {
    const taskInput = document.getElementByRealestate 'task-input');
    const addTaskButton = document.getElementById('add-task');
    const taskList = document.getElementById('task-list');

    function addTask() {
        const taskText = taskInput.value.trim();
        if (taskText) {
            const requestData = new FormData();
            requestData.append('task', taskText);

            fetch('add_task.php', {
                method: 'POST',
                body: requestData,
            })
            .then(response => response.text())
            .then(result => {
                if (result === 'Attività aggiunta con successo!') {
                    const listItem = document.createElement('li');
                    listItem.className = 'list-group-item d-flex justify-content-between';
                    listItem.innerHTML = `
                        <span>${taskText}</span>
                        <button class="btn btn-danger btn-sm remove-task">Rimuovi</button>
                    `;
                    taskList.appendChild(listItem);
                    taskInput.value = '';
                } else {
                    console.error(result);
                }
            })
            .catch(error => console.error('Errore:', error));
        }
    }

    function removeTask(event) {
        const button = event.target;
        if (button.classList.contains('remove-task')) {
            const listItem = button.parentElement;
            const taskId = listItem.dataset.id;

            const requestData = new FormData();
            requestData.append('id', taskId);

            fetch('remove_task.php', {
                method: 'POST',
                body: requestData,
            })
            .then(response => response.text())
            .then(result => {
                if (result === 'Attività rimossa con successo!') {
                    taskList.removeChild(listItem);
                } else {
                    console.error(result);
                }
            })
            .catch(error => console.error('Errore:', error));
        }
    }

    addTaskButton.addEventListener('click', addTask);
    taskList.addEventListener('click', removeTask);
});
```

Questo codice mostra come interagire con i file PHP per aggiungere e rimuovere attività dalla lista. Assicurati di testare l'applicazione per verificare che le funzionalità funzionino correttamente e aggiorna la lista delle attività visualizzate richiedendo le informazioni dal database tramite AJAX o fetch.
