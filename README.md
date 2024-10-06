# Event Management System

## Descrizione del Progetto
Un sistema di gestione degli eventi in cui gli utenti possono registrarsi, effettuare il login, creare eventi, gestire i partecipanti e vedere i dettagli degli eventi. Gli utenti possono avere ruoli diversi (admin, organizzatore e partecipante) e le autorizzazioni variano in base al ruolo.

## Funzionalità Principali
1. **Autenticazione e Registrazione**
   - Implementare il sistema di login, registrazione e reimpostazione della password utilizzando le funzionalità integrate di Laravel (Laravel Breeze o Jetstream).
   - Differenti ruoli utente: admin, organizzatore, partecipante.
   
2. **Dashboard e Profili Utente**
   - Creare una dashboard personalizzata per gli utenti, mostrando i dettagli degli eventi a cui partecipano.
   - Sezione profilo per aggiornare le informazioni personali (nome, email, immagine profilo, ecc.).

3. **Gestione degli Eventi**
   - Creare, aggiornare e cancellare eventi (CRUD).
   - Aggiungere descrizioni, date, orari, luoghi e immagini per gli eventi.

4. **Partecipazione agli Eventi**
   - Gli utenti possono registrarsi a un evento.
   - Visualizzare l'elenco dei partecipanti per ciascun evento.

5. **Amministrazione**
   - Solo gli utenti con ruolo di admin possono accedere a una dashboard di amministrazione.
   - Gestione utenti: gli admin possono vedere, aggiornare e rimuovere utenti.
   - Gestione degli eventi: approvare o rimuovere eventi creati dagli organizzatori.

6. **Middleware e Permessi**
   - Utilizzare i middleware per proteggere le rotte in base ai ruoli utente.
   - Creare policy e gate per definire l'accesso alle diverse funzionalità in base al ruolo.

7. **Notifiche e Email**
   - Inviare email di conferma quando un utente si iscrive a un evento.
   - Notifiche in tempo reale (utilizzando Laravel Echo e Pusher) per avvisare gli utenti di nuove modifiche agli eventi.

8. **Utilizzo di Blade e Componenti**
   - Utilizzare Blade per creare viste dinamiche e interattive.
   - Creare componenti Blade riutilizzabili per moduli, carte di eventi e layout della pagina.

9. **Database e Relazioni**
   - Tabelle per utenti, eventi e partecipazioni (relazione molti-a-molti tra utenti ed eventi).
   - Utilizzare le migrazioni per creare le tabelle.
   - Eloquent ORM per gestire le relazioni tra i modelli.

10. **API e AJAX**
    - Creare API per permettere ad altri client (es. una SPA o un'app mobile) di interagire con il sistema.
    - Utilizzare AJAX per operazioni asincrone come la registrazione a un evento.

11. **Interfaccia Utente**
    - Utilizzare Bootstrap, TailwindCSS o un altro framework CSS per creare un'interfaccia utente pulita e responsiva.

## Struttura delle Tabelle nel Database

### Users
- `id`
- `name`
- `email`
- `password`
- `role` (admin, organizer, participant)
- `created_at`
- `updated_at`

### Events
- `id`
- `title`
- `description`
- `date`
- `location`
- `image`
- `created_by` (id dell'organizzatore)
- `created_at`
- `updated_at`

### Event_User (tabella pivot)
- `id`
- `user_id`
- `event_id`
- `created_at`
- `updated_at`

## Rotte Principali
- `/login`: Form di login.
- `/register`: Form di registrazione.
- `/dashboard`: Dashboard utente (diversa per admin, organizzatore e partecipante).
- `/events`: Elenco degli eventi.
- `/events/create`: Creazione di un nuovo evento (solo per organizzatori).
- `/events/{id}`: Dettaglio dell'evento.
- `/events/{id}/edit`: Modifica dell'evento (solo organizzatori/admin).
- `/admin`: Dashboard di amministrazione (solo per admin).

## Risultati Attesi
Alla fine del progetto, acquisirai familiarità con molte delle funzionalità di Laravel, inclusi:
- Routing
- Controller e middleware
- Gestione di Blade e dei componenti
- Gestione del database con migrazioni e Eloquent ORM
- Autenticazione e autorizzazione (ruoli e permessi)
- Gestione di notifiche e email
- Creazione di API e gestione di chiamate AJAX
- Gestione di eventi real-time con Echo (facoltativo).

## Tecnologie Utilizzate
- **Laravel** (Framework backend)
- **MySQL** (Database)
- **Blade** (Templating engine)
- **Bootstrap** o **TailwindCSS** (Styling)
- **Laravel Echo & Pusher** (Notifiche in tempo reale, opzionale)
- **AJAX** per richieste asincrone
