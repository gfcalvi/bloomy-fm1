# Bloomy 1.1.0 — release a cinque slot

Firmware hardware compilato: app 581404 B, 160 B liberi; RAM 97352 B, 952 B liberi; 16 voci e blocchi 256 frame invariati. Loader 8591 B, invariato. Palette delle tracce conservata. Banco campioni 104 KiB, fabbrica 90505 B.

Verifiche software PASS:
- Codice C reale di storage: pieno payload 3840 B nell’oggetto aggiuntivo, 25 scritture interrotte, recupero A/B e aree riservate al loader preservate.
- Codice C reale di Backup/Restore: 175 interruzioni di scrittura, sempre insieme precedente o nuovo completo; calibrazione preservata.
- Cinque progetti distinti salvati, caricati e riaperti nel simulatore nativo; core RemoteFM1 conserva byte per byte tutti e cinque e il banco dopo boot/sync.
- Migrazione Python/JavaScript identica; audio ADPCM, checkpoint, indici e metadati preservati. Banco sovradimensionato e file corrotti rifiutati.
- Dieci andate/ritorni nei formati a tre/cinque slot; contenitore RemoteFM1 con core qualificato corrispondente. TXT senza banco come nel formato originale.
- 77 controlli di script, merge fra sorgenti e destinazioni, estrazione/ricomposizione, annullamento, backup facoltativo e lettura diretta, backup non corrispondente, dati modificati durante la conferma, identità errata, esiti Restore e rilettura errata, payload speciale nel .fm1save.
- Cinque trasferimenti SysEx completi con dispositivo simulato e verifica degli altri slot.
- Ritorno a tre slot con progetti 4/5 conservati in file separati; errore campioni/disconnessione e rilettura errata segnalati.
- Quindici percorsi DOM in Chrome: selettori e libreria quinto slot, estrazione, conversione, caricamento legacy, Backup, hash installazione e rollback.
- Emulatore web WASM: 38 oggetti, cinque progetti, riproduzione audio senza saturazione e oggetti salvati conservati.
- Otto prove precedenti della pagina Migrazione 3/5 offline.

Collaudo utente: circa tre ore di uso intenso su FM-1 con caricamento/salvataggio brani senza problemi; iPhone positivo. Migrazione di contenuti e ritorno a tre slot esclusi espressamente dai requisiti dell’utente; non sono pagine della suite corrente. Nessuna scrittura hardware effettuata dall’agente.

Il servizio USB Backup del dispositivo non è implementato nell’adattatore RemoteFM1: il tentativo di collaudarlo attraverso quel core è stato escluso, con timeout atteso. Le prove del protocollo sono quelle C e JavaScript separate sopra; il core è collaudato per audio/salvataggi.

Release predefinita: Bloomy 1.1.0, strumenti 2.0.1. Salva brano è un nuovo percorso software: il suo export singolo viene verificato separatamente. Nessun backup personale è incluso.

Salva brano: nove prove DOM PASS in Chrome con MIDI simulato, inclusi export di ciascuno dei cinque slot, confronto di sette oggetti e campioni, cambio nome e disconnessione. Il nuovo percorso Salva brano non è stato ancora riferito come provato su hardware dall’utente.
