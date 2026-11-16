# Bloomy 1.1.2 / tools 2.0.5 — verifiche

- Build target PASS: app581420B/581564; RAM97336/98304; pool334384/344064.16voci,5slot,104KiB campioni.
- Host PASS: note250, riavvio, due slot con note diverse, consultazione/scorrimento/uscita e layout.
- Metadati PASS, test DOM salvataggio inclusi rilettura ritardata e mancata risposta senza doppia scrittura.
-6test verifica differita PASS; test protocolloMIDI riproduce lettura immediata persa e verifica successiva riuscita, scrittura una sola volta.
-Host navigazioneNote con testi brevi/lunghi: SELECT esce ai bordi, passa fra Setup/Note/Mix.
- Roundtrip .loom8, TXT (+LSMP), .rfm1state, .fm1save PASS; musica/altri slot/campioni conservati.
- RemoteFM1 1.1.2 boot e sync PASS; WebWASM1.1.2 boot 38 oggetti PASS.
- Installazione diretta:5DOMPASS inChrome, ciclo OTA simulato, resume, resume, annullamento e rifiutovecchioformato. Zero richieste backup/restore nei pacchetti MIDI simulati.
- Updater effettivo estratto dalla pagina: test porte/protocollo/CRC PASS.
- Due build seriali: app e loader byte-identici; loader uguale alla1.1.0 collaudata salvo il testo versione. Check-native blocca packaging se diverso dal riferimento.
- Installer Chrome: SHA256 verificato; nessun MIDI reale o flash eseguito.
- Hardware fisico e iPhone per questa revisione NOT_RUN; 1.1.0 resta predefinita.

Formato24 richiede1.1.1 o1.1.2. Il titolo è11caratteri; note250 ASCII/newline. Le note vengono conservate nel settingsobject dello slot, con CRC già previsto dall'archivio. I tools rifiutano note troppo lunghe o con caratteri non supportati e verificano capienza3840B prima di scrivere. Non vengono troncate.
