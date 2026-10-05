# SoBigData Summer School Website

Questo repository contiene il sito web della Summer School SoBigData 2026, sviluppato con Jekyll.

## Pipeline di Pubblicazione

La pipeline di pubblicazione è strutturata su tre ambienti: Sviluppo (dev), Certificazione (cert) e Produzione.

### Ambiente di Sviluppo (Branch: dev)

In questo ambiente vengono sviluppate e testate tutte le modifiche al sito.

1. Per avviare il server di sviluppo in locale:
   ```bash
   bundle exec jekyll serve --config _config.yml,_config_dev.yml
   ```

2. Verifica le modifiche all'indirizzo `http://localhost:4000`

### Ambiente di Certificazione (Branch: cert)

L'ambiente di certificazione è ospitato su GitHub Pages e permette la revisione delle modifiche da parte dei responsabili.

1. Per pubblicare le modifiche in certificazione:
   ```bash
   git checkout cert
   git merge dev
   ```

2. Le modifiche saranno automaticamente visibili all'indirizzo:  
   https://danielefadda.github.io/sobigdata-summer-school-2026/

### Ambiente di Produzione

Una volta approvate le modifiche in certificazione, è possibile procedere con la pubblicazione in produzione.

1. Assicurarsi di essere sul branch cert:
   ```bash
   git checkout cert
   ```

2. Generare i file statici:
   ```bash
   bundle exec jekyll build --config _config.yml,_config_dist.yml
   ```
   I file verranno generati nella cartella `_site`

3. Pubblicare il sito in produzione via SSH:
   ```bash
   # Esempio di comando scp (da adattare in base alla configurazione del server)
   scp -r _site/* user@server:/path/to/sobigdata-summerschool2026/
   ```

4. Il sito sarà disponibile all'indirizzo:  
   https://summerschool2026.sobigdata.eu/

## Struttura delle Configurazioni

Il sito utilizza file di configurazione specifici per ogni ambiente:

- `_config.yml`: Configurazione base comune a tutti gli ambienti
- `_config_dev.yml`: Configurazioni specifiche per l'ambiente di sviluppo
- `_config_dist.yml`: Configurazioni specifiche per l'ambiente di produzione

## Note Importanti

- Effettuare sempre i test in ambiente locale (dev) prima di procedere con il merge in certificazione
- Attendere l'approvazione dei responsabili prima di procedere con la pubblicazione in produzione
- Mantenere aggiornata la documentazione in caso di modifiche alla pipeline di deployment