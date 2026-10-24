# archteathos.it: GitHub Pages e posta Aruba

Repository dedicato: `https://github.com/CELOTTOA/archteathos-landing`. Pubblicazione da `main`, cartella `/`. Dominio da associare nelle impostazioni Pages: `archteathos.it`. Contatto pubblico: `info@archteathos.it`.

## DNS rilevati il 24 ottobre 2026

- A di archteathos.it: `62.149.128.40` (pagina di servizio Aruba).
- CNAME di www.archteathos.it: `archteathos.it`.
- MX: `mx.archteathos.it`, priorità 10.
- SPF: `v=spf1 include:_spf.aruba.it ~all`.
- DMARC: `v=DMARC1; p=none; adkim=r; aspf=r;`.
- Nessun AAAA rilevato sul dominio principale.
- Name server: `dns.technorail.com`, `dns2.technorail.com`, `dns3.arubadns.net`, `dns4.arubadns.cz`.

## Record web da impostare su Aruba

Il dominio personalizzato deve essere già associato al repository nelle impostazioni GitHub Pages prima di applicare i DNS. Nel pannello Aruba, Gestione DNS, sostituire il vecchio A del dominio principale con questi quattro A e aggiornare soltanto il CNAME di www:

| Tipo | Host Aruba | Valore | TTL |
| --- | --- | --- | --- |
| A | vuoto (dominio principale) | 185.199.108.153 | 3600 |
| A | vuoto (dominio principale) | 185.199.109.153 | 3600 |
| A | vuoto (dominio principale) | 185.199.110.153 | 3600 |
| A | vuoto (dominio principale) | 185.199.111.153 | 3600 |
| CNAME | www | celottoa.github.io | 3600 |

Non inserire https o il nome del repository nel CNAME. Mantenere i name server Aruba e i record della posta: MX, SPF, DKIM, DMARC, mx, mail, smtp, imap, pop3, webmail, autodiscover e autoconfig se presenti. Non caricare una nuova zona completa: modificare soltanto i puntamenti web elencati.

Dopo la propagazione, verificare il controllo DNS su GitHub Pages, attendere il rilascio del certificato e attivare Enforce HTTPS quando disponibile. Verificare sia archteathos.it sia www.archteathos.it. La propagazione DNS può richiedere fino a 24 ore.

## Riferimenti

- [GitHub: dominio personalizzato](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
- [Aruba: record A](https://guide.aruba.it/hosting-e-domini/gestione-dns/gestione-name-server-e-record/gestire-record-a)
- [Aruba: record CNAME](https://guide.aruba.it/hosting-e-domini/gestione-dns/gestione-name-server-e-record/gestire-record-cname)
