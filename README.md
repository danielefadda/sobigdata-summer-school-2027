# SoBigData Summer School Website

Questo repository contiene il sito web della Summer School SoBigData 2027, sviluppato con Jekyll.

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
   https://danielefadda.github.io/sobigdata-summer-school-2027/

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
   scp -r _site/* user@server:/path/to/sobigdata-summerschool2027/
   ```

4. Il sito sarà disponibile all'indirizzo:  
   https://summerschool2027.sobigdata.eu/

## Struttura delle Configurazioni

Il sito utilizza file di configurazione specifici per ogni ambiente:

- `_config.yml`: Configurazione base comune a tutti gli ambienti
- `_config_dev.yml`: Configurazioni specifiche per l'ambiente di sviluppo
- `_config_dist.yml`: Configurazioni specifiche per l'ambiente di produzione

## Link relativi

I plugin in `_plugins/` (importati da [sbd-master-website](https://github.com/danielefadda/sbd-master-website)) ridefiniscono il filtro `relative_url`:

- `pure_relative_paths: false` (default in `_config.yml`, usato da `jekyll serve` e da GitHub Pages, che ignora i plugin custom): `relative_url` si comporta come lo standard Jekyll e usa `baseurl`.
- `pure_relative_paths: true` (attivo in `_config_dist.yml` e `_config_dist_test.yml`): `relative_url` genera percorsi relativi alla pagina corrente (es. `assets/...`, `../assets/...`), quindi il sito funziona da qualsiasi sottocartella indipendentemente da `baseurl`. I link interni assoluti generati dal tema (CSS, feed, gallerie) vengono resi relativi in post-render; canonical, `og:` e JSON-LD restano assoluti.

Regole pratiche:

- Per pagine e asset interni usare sempre `relative_url`:
   - `{{ '/venue.html' | relative_url }}`
   - `{{ '/assets/images/logo.png' | relative_url }}`
   - con variabili: `{{ speaker.img_url | relative_url }}`, `{{ '/assets/charts/' | append: chart | relative_url }}`
- Non usare `{{ site.baseurl }}/...` né percorsi hardcoded che iniziano con `/` dentro `href` o `src`.
- Usare `absolute_url` solo dove serve un URL completo (es. `og:image`, servizi esterni).
- Per link esterni (`https://...`) lasciare l'URL completo senza filtri.

## Note Importanti

- Effettuare sempre i test in ambiente locale (dev) prima di procedere con il merge in certificazione
- Attendere l'approvazione dei responsabili prima di procedere con la pubblicazione in produzione
- Mantenere aggiornata la documentazione in caso di modifiche alla pipeline di deployment