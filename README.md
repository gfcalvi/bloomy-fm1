# Bloomy Tools 2.2.0

https://gfcalvi.github.io/bloomy-fm1/

Firmware1.2.0 invariato. La novità è **Sostituisci traccia**.

## Sostituire il basso della propria r7 con quello della r10

1. Salva/esporta il tuo progetto modificato con Salva brano.
2. Apri Sostituisci traccia: a sinistra scegli **la tua r7 modificata**, a destra la r10.
3. Scegli T2 in entrambe le colonne. Lascia attiva **Copia anche le assegnazioni nelle scene**: serve al ciclo XXX2XXX1.
4. Premi Crea progetto con traccia sostituita, poi Salva .bloomyproject (o Condividi/Salva su File su iOS).
5. Usa Carica brano per inserire il nuovo progetto nello slot desiderato.

Le altre tracce, titolo/note, tempo, Song, Conductor, Weave globale, libreria e banco campioni restano quelli del progetto base. Suono, otto pattern, automazioni, Turing/Evolver e pattern/mute nelle scene della traccia scelta arrivano dalla sorgente. Gli effetti master restano quelli del progetto base: le mandate importate usano quegli effetti.

Le Song devono avere sezioni corrispondenti per numero e durata; i numeri delle scene possono differire. Una scena riutilizzata con assegnazioni sorgente in conflitto viene bloccata. Si può scegliere di mantenere le assegnazioni delle scene del progetto base, disattivando la casella. Due progetti senza Song devono avere le stesse scene presenti.

Per conservare i mute dei kit sono ammessi trasferimenti melodica→melodica o Kit→Kit. Campioni usati dalla traccia devono coincidere nei banchi dei due progetti; nessun banco viene sostituito. Formati progetto23/24 qualificati; per file più vecchi aprire/salvare prima con Bloomy aggiornato.

## Mac, iPhone/iPad e offline

Mac: apri il sito con Chrome/Edge. Il pacchetto ZIP contiene anche index.html con tutti gli otto strumenti incorporati: puoi aprirlo con Chrome senza server locale. I file personali vengono elaborati sul dispositivo.

iPhone/iPad: apri il sito in MIDIWeb Browser e usa **Make Available Offline**. Dopo l’aggiornamento sostituisci la copia offline e verifica **Strumenti2.2.0**. Questa procedura non richiede un Mac acceso. L’apertura diretta file:// da Files in MIDIWeb Browser dipende dall’app e non è il percorso consigliato.

La pagina Sostituisci-traccia.html è autonoma e funziona anche salvata offline. Non usa Web MIDI e non scrive sull’FM-1. Non carica file su server e non richiede login.

Manuale PDF edizione16 ed emulatore sono download separati, non inclusi nel pacchetto tools compatto. La guida della nuova funzione è questa; il PDF precedente non è stato modificato. Tutte le istruzioni di installazione degli strumenti precedenti restano valide.
