# Bloomy 1.1.1 / tools 2.0.4 — verifiche

- Build target PASS: app581516B/581564; RAM97336/98304; pool334384/344064.16voci,5slot,104KiB campioni.
- Host PASS: note250, riavvio, due slot con note diverse, consultazione/scorrimento/uscita e layout.
- 12 test metadati PASS, 12 DOM in Chrome con MIDI simulato PASS.
- Roundtrip .loom8, TXT (+LSMP), .rfm1state, .fm1save PASS; musica/altri slot/campioni conservati.
- RemoteFM1 1.1.1 boot e sync PASS; WebWASM1.1.1 boot 38 oggetti PASS.
- Installazione diretta:5DOMPASS inChrome, ciclo1.1.0→loader→1.1.1, resume, annullamento e rifiutovecchioformato. Zero richieste backup/restore nei pacchetti MIDI simulati.
- Updater effettivo estratto dalla pagina: test porte/protocollo/CRC PASS.
- Due build seriali: app e loader byte-identici; loader uguale alla1.1.0 collaudata salvo un byte del testo versione. Check-native blocca packaging se diverso dal riferimento.
- Installer Chrome: SHA256 verificato; nessun MIDI reale o flash eseguito.
- Hardware fisico e iPhone per questa revisione NOT_RUN; 1.1.0 resta predefinita.

Formato24 richiede1.1.1. Il titolo è11caratteri; note250 ASCII/newline. Le note vengono conservate nel settingsobject dello slot, con CRC già previsto dall'archivio. I tools rifiutano note troppo lunghe o con caratteri non supportati e verificano capienza3840B prima di scrivere. Non vengono troncate.
