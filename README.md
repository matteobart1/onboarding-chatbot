# Chatbot n8n statico

Questa è una pagina statica che incorpora il widget `@n8n/chat` seguendo le linee guida del pacchetto [`@n8n/chat`](https://www.npmjs.com/package/@n8n/chat).

## Requisiti lato n8n
- Flusso n8n con nodo "N8N Chat Trigger" esposto pubblicamente (HTTPS)
- URL pubblico del webhook (es. `https://<tuo dominio>/webhook/chat/<route>`)

## Configurazione
1. Apri `index.html`
2. Sostituisci il placeholder `WEBHOOK_URL` con il tuo URL pubblico del webhook n8n
3. (Opzionale) Personalizza titolo, tema, messaggio iniziale, ecc.

## Avvio locale
Puoi aprire direttamente `index.html` nel browser oppure servire la cartella con un server statico:

```bash
npx serve .
```

Se la tua istanza n8n non è pubblica, usa un tunnel (es. `cloudflared`, `ngrok`) verso n8n.

## Deploy
Questa cartella è pubblicabile come sito statico. Opzioni comuni:

- GitHub Pages: abilita Pages sul branch `main`/`docs` e pubblica la root.
- Netlify: trascina e rilascia la cartella o collega il repo (build command: none, publish dir: root).
- Vercel: import del repo, framework `Other`, output directory `./`.

## Note di sicurezza
- Non inserire segreti nel frontend: il widget chiama solo l'endpoint pubblico del tuo n8n.
- Abilita rate limiting e validazioni nel tuo flusso n8n secondo necessità.

