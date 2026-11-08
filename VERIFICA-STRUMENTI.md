# Verifica strumenti Bloomy — revisione 1.2

Esito: **66 casi PASS, 0 FAIL** sull'ultima build. Firmware 1.0.0-blue invariato.

| Gruppo | Casi | Ambiente |
|---|---:|---|
| Percorsi UI completi | 29 | Browser desktop, DOM reale, File/FileReader e Blob; MIDI simulato |
| Protocollo backup e campioni | 14 | Node, risposte di FM-1 simulato sul codice della pagina generata |
| Formati e condizioni di sicurezza | 23 | Node, backup reale e vecchio stato Blue 0.9.5 compresso |

La UI verifica selezione file, riepilogo, conversione e contenuto dei download nei quattro formati,
allegato LSMP, invalidazione di risultati precedenti, estrazione dei tre slot e ricomposizione
byte per byte, consenso al Restore, annullamento, STOP FIRST/HOME, autorizzazione negata,
firmware/banco corrotti, consenso backup prima dell'installazione, errore di preparazione,
crash report, file stock non valido e blocco delle schede durante un'operazione.
I trasferimenti hardware dei test UI sono sostituiti da simulazioni; i Blob risultanti sono
controllati prima del salvataggio nativo del sistema operativo.

Il protocollo viene verificato separatamente: backup/restore identici, domanda sul dispositivo,
STOP FIRST/HOME senza applicare dati, file corrotto senza inviare restore, frame perso,
timeout, disconnessione, identità firmware diversa, struttura oggetti errata, trasferimento
campioni identico, banco vuoto/erase, campioni corrotti senza scrivere, errore di scrittura,
risposte campioni perse o ritardate con retry.

I formati coprono tutte le 16 combinazioni fra loom8/TXT/rfm1state/fm1save con confronto
dei dati musicali e del banco quando il formato lo conserva. Altri casi: SHA senza crypto,
consenso alla perdita del banco TXT, SHA stato errato, core sconosciuto, settore fm1save
alterato, stato compresso Blue 0.9.5 e blocco della sovrascrittura dei campioni quando la
lettura dopo l'installazione fallisce. I fixture privati non sono distribuiti nel pacchetto.

## Correzioni incluse

- SHA-256 portabile, senza saltare il controllo; verifica del banco prima di abilitare Install.
- Accesso MIDI tramite documento principale nei riquadri; Restore con conferma interna alla pagina.
- Filtri di estensione rimossi dai selettori; la validazione del contenuto rimane attiva.
- Blocco delle operazioni concorrenti, comprese sonde porte e crash report.
- Invalidazione delle letture file superate; struttura dei backup e sezioni extra controllate.
- Errori delle API opzionali di condivisione non invalidano una conversione riuscita.
- Fallimento della preparazione dei campioni blocca il flash; una lettura fallita dopo il flash
  non diventa un banco vuoto da sovrascrivere.
- Build unica riproducibile per suite e pagine dirette, senza patch manuali divergenti.

## Limiti e prove reali

L'utente ha confermato apertura offline, SHA verificato e Backup/Restore sul proprio iPhone.
Non è stato specificato se l'ultimo Backup/Restore fosse eseguito con tutte le reti disattivate.
Questi risultati non equivalgono alla verifica di ogni dispositivo iOS, del provider Dropbox,
della conservazione di MIDIWeb dopo aggiornamenti dell'app, o delle temporizzazioni USB reali.
Nessuna operazione di scrittura hardware è stata eseguita dall'agente durante questa revisione.
Il firmware non è stato ricompilato, la sua identità e i dati musicali non sono stati modificati.

Log integrali e harness ripetibili: cartella Strumenti/QA del progetto. Sorgenti canonici:
Strumenti/Suite-source e Strumenti/build-offline-suite.py. Il pacchetto include i sorgenti
HTML e il builder; i test con dati personali rimangono nel progetto locale.
