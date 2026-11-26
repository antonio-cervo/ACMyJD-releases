# Informativa sulla privacy — JD Link Sender

*English version: [PRIVACY.en.md](PRIVACY.en.md)*

Ultimo aggiornamento: 2026-11-26

JD Link Sender è un'estensione per browser che invia link e container crittografati a un'istanza
di JDownloader 2 (interfaccia ClickNLoad2) scelta e configurata dall'utente.

## Dati trattati

- **Contenuto delle pagine web**: quando l'utente clicca esplicitamente sulla voce di menu
  contestuale "Invia a JDownloader" (su un link, una selezione di testo o un'area della pagina),
  sull'icona dell'estensione o usa la sua scorciatoia da tastiera, l'estensione legge il contenuto HTML/DOM di quella pagina o link per individuare blocchi CNL2
  crittografati, liste di link e l'eventuale password degli archivi ("Password: …"), che viene
  proposta nel popup e inviata solo a JDownloader. Questa lettura avviene solo su azione esplicita dell'utente, mai
  in background o su pagine non selezionate.
- **Richieste Click'n'Load dei siti**: quando un sito invia link al JDownloader locale
  (`http://127.0.0.1:9666/flash/...`), di solito perché l'utente ha premuto il suo pulsante
  Click'n'Load, l'estensione legge i dati di quella sola richiesta (link o container
  crittografato) e li propone nel popup di conferma. Nessun'altra richiesta di rete viene letta.
  La funzione si può disattivare dalla pagina Opzioni.
- **Configurazione JDownloader**: l'URL (e l'eventuale URL di riserva) dell'istanza JDownloader inserito dall'utente nella pagina
  Opzioni viene salvato nello storage sincronizzato del browser (`chrome.storage.sync`), legato al
  proprio account/profilo browser, per essere riutilizzato tra le sessioni.
- **Stato temporaneo del popup**: i link/container da confermare vengono passati dallo script di
  background al popup di conferma tramite lo storage di sessione del browser
  (`chrome.storage.session`), e cancellati subito dopo la lettura.
- **Cronologia invii e preferenze hoster**: gli indirizzi dei link inviati con il nome del
  pacchetto (per i container crittografati solo un'impronta SHA-256, non il contenuto) e gli hoster deselezionati
  dall'utente vengono salvati nello storage locale del browser (`chrome.storage.local`, non
  sincronizzato), per segnalare i link già inviati e riproporre le scelte fatte. Le voci della
  cronologia scadono dopo 60 giorni e possono essere cancellate in qualsiasi momento dalla pagina
  Opzioni. Questi dati non lasciano mai il browser.
- **Invii in attesa**: se JDownloader non è raggiungibile, i link (o i container crittografati)
  da inviare, con l'eventuale password dell'archivio, restano nello storage locale del browser (`chrome.storage.local`) finché l'invio
  non riesce o l'utente non li toglie dalla pagina Opzioni. Vengono inviati solo all'istanza
  JDownloader configurata.

## Dove vanno i dati

I link e i container estratti vengono inviati **esclusivamente** all'istanza JDownloader indicata
dall'utente stesso nella pagina Opzioni (in rete locale o remota, ad es. tramite un tunnel di
proprietà dell'utente). Nessun dato viene inviato agli sviluppatori dell'estensione o a server di
terze parti.

## Condivisione dei dati

Non vendiamo, non trasferiamo e non condividiamo alcun dato utente con terze parti. Non
utilizziamo i dati per finalità pubblicitarie, di profilazione, di valutazione del credito o di
prestito.

## Contatti

Per domande su questa informativa, apri una issue su
https://github.com/antonio-cervo/ACMyJD-releases/issues
