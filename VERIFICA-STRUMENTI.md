# Bloomy 1.2.0 - verifiche release

Firmware identico al candidato collaudato dall’utente: dedf1138f43480b68ff1d693da7126600178317b8fe1606e33eb34641441e87a

Collaudo hardware utente positivo, compresi Size/Decay/Shimmer al massimo senza rumori anomali. Nessuna nuova scrittura hardware effettuata dall’agente. Nessuna misura numerica CPU acquisita.

Due build native identiche; loader di riferimento verificato; ASAN/UBSAN; 15 effetti precedenti byte-identici; cinque slot save/load; codec round-trip e boot RemoteFM1; installatore simulato; render WAV deterministico, somma stem+FX e cancellazione verificati.

Shimmer comune al bus FX II; non esiste send separato della componente trasposta per traccia.

Tools2.1.1: MP3encoder160kbps/stereo44100, ogniheaderframeverificato; durata, determinismo, annullamento eWAV16bitverificati. Song112bar@74BPM durata363.253s verificata, primo slot4barconservato. Testbrowserworker/ZIP/AudioContextdecode, PCMnon-silenzioso ecomandiUI. Firmware invariato. ProvaMP3suiOSfisicoNONeseguita dall’agente.

Tools2.1.2: MP3encoder160kbps/stereo44100, ogniheaderframeverificato; durata, determinismo, annullamento eWAV16bitverificati. Song112bar@74BPM durata363.253s verificata, primo slot4barconservato. Testbrowserworker/ZIP/AudioContextdecode, PCMnon-silenzioso ecomandiUI. Firmware invariato. ProvaMP3suiOSfisicoNONeseguita dall’agente. Tools2.1.2: nomiZIP/MP3/WAV eRapporto coerenti; fallbacktitolo perslot/filename, caratteripericolosi e nomiriservati gestiti; 7browserPASS e unitnamesPASS.
