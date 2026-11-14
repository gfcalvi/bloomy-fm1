# Bloomy — strumenti 1.5

Firmware 1.0.1 invariato. Manuale edizione 13. Nessuna scrittura hardware eseguita dall’agente.

Carica brano legge l’archivio salvato, sostituisce i sette oggetti dello slot scelto,
conserva gli altri due slot e la libreria preset. Il banco campioni non viene scritto.
Confronto di compatibilità dei campioni, backup preventivo scaricabile, conferma
interna alla pagina, rilettura prima dell’invio e verifica completa dopo il ripristino.
Usa il protocollo journalled già esistente: non richiede firmware nuovo.

105 casi software PASS, 0 FAIL:
- 34 percorsi nelle pagine reali di Chrome, con MIDI simulato (29 precedenti + 5 nuovi).
- 19 casi di importazione/merge: cinque formati, tutte le destinazioni, slot vuoto,
  CRC, dati compressi, campioni incompatibili e vecchio RemoteFM1 compresso.
- 12 casi del controller di caricamento: conferma/annulla, STOP/HOME/errori,
  cambiamenti del dispositivo, disconnessione, rilettura errata e condivisione iOS opzionale.
- 3 trasferimenti SysEx completi verso ciascuno slot con dispositivo simulato,
  conferma hardware simulata e confronto byte per byte degli altri slot.
- 23 regressioni formati/sicurezza e 14 regressioni del protocollo backup/campioni.

Le simulazioni non sono misure delle temporizzazioni USB dell’iPhone o del chip.
L’utente aveva confermato Backup/Restore e uso offline su iPhone; il nuovo percorso
Carica brano non è ancora stato provato fisicamente su iPhone/FM-1.

File TXT senza banco: usa i campioni esistenti; i soli parametri non identificano
l’audio originale. Per campioni personalizzati preferire un backup con LSMP.

Sorgenti e builder inclusi. Fixture e backup privati non distribuiti.
