# 🎙️ Voice Transcription Studio

**App completa per registrazione vocale, trascrizione AI e generazione mappe mentali**

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![React](https://img.shields.io/badge/React-18.2.0-61dafb.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## ✨ Funzionalità

- 🎤 **Registrazione Audio**: Registrazione di alta qualità con timer
- 🤖 **Trascrizione AI**: Conversione automatica da audio a testo strutturato
- 🧠 **Mappe Mentali**: Generazione automatica di mindmap interattive
- 💾 **Storage Persistente**: Salvataggio locale con IndexedDB
- 📱 **Design Responsive**: Ottimizzato per mobile, tablet e desktop
- 📧 **Condivisione Email**: Invio diretto dei file generati
- 🎨 **UI Moderna**: Design accattivante con animazioni fluide

## 🚀 Demo Live

👉 **[Prova l'App Online](https://robertomicarelli.github.io/voice-transcription-app/)**

## 📋 Prerequisiti

- **Node.js** >= 16.0.0
- **npm** >= 8.0.0
- **Git** per il version control
- **Account GitHub** per il deploy

## 🛠️ Installazione Rapida

### 1. Clona il Repository

```bash
git clone https://github.com/TUO-USERNAME/voice-transcription-app.git
cd voice-transcription-app
```

### 2. Installa Dipendenze

```bash
npm install
```

### 3. Configurazione Ambiente

```bash
# Copia il file di esempio
cp .env.example .env

# Modifica .env con le tue API keys (opzionale)
nano .env
```

### 4. Avvio Sviluppo

```bash
npm start
```

L'app sarà disponibile su `http://localhost:3000`

## 🔧 Configurazione Avanzata

### API Keys (Opzionale)

Per funzionalità complete, configura le seguenti API:

1. **OpenAI API** (per trascrizioni reali):
   ```bash
   REACT_APP_OPENAI_API_KEY=sk-your-openai-key-here
   ```

2. **Markmap API** (per mappe mentali avanzate):
   ```bash
   REACT_APP_MARKMAP_API=https://markmap.js.org/api
   ```

**Nota**: L'app funziona anche senza API keys in modalità demo!

## 🌐 Deploy su GitHub Pages

### Metodo 1: Deploy Automatico (Raccomandato)

1. **Crea Repository GitHub**:
   ```bash
   # Su GitHub.com crea nuovo repository 'voice-transcription-app'
   git remote add origin https://github.com/TUO-USERNAME/voice-transcription-app.git
   ```

2. **Configura package.json**:
   ```json
   {
     "homepage": "https://TUO-USERNAME.github.io/voice-transcription-app"
   }
   ```

3. **Push e Deploy**:
   ```bash
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   
   # Deploy automatico
   npm run deploy
   ```

### Metodo 2: GitHub Actions (CI/CD)

Il file `.github/workflows/deploy.yml` è già configurato:

1. **Push su GitHub**:
   ```bash
   git add .
   git commit -m "Setup GitHub Actions"
   git push origin main
   ```

2. **Abilita GitHub Pages**:
   - Vai su GitHub → Settings → Pages
   - Source: "Deploy from a branch"
   - Branch: `gh-pages`

3. **Deploy Automatico**: Ad ogni push su `main`, l'app si aggiorna automaticamente!

## 📁 Struttura Progetto

```
voice-transcription-app/
├── public/
│   ├── index.html              # HTML principale
│   ├── manifest.json           # PWA config
│   └── favicon.ico
├── src/
│   ├── components/             # Componenti React
│   ├── services/              
│   │   ├── audioService.js     # Gestione registrazioni
│   │   ├── transcriptionService.js  # API trascrizioni
│   │   └── mindmapService.js   # Generazione mappe
│   ├── utils/
│   │   └── storage.js          # Database locale
│   ├── App.js                  # Componente principale
│   ├── App.css                 # Stili personalizzati
│   └── index.js
├── .github/workflows/
│   └── deploy.yml              # CI/CD GitHub Actions
├── package.json
├── README.md
└── .env                        # Configurazione API
```

## 🎯 Come Usare l'App

### 1. Prima Registrazione
- Clicca "Inizia Registrazione"
- Autorizza accesso microfono
- Parla normalmente
- Clicca "Ferma Registrazione"

### 2. Visualizza Risultati
- Vai in "Storico Registrazioni"
- Clicca su una registrazione
- Esplora: Audio, Trascrizione, Mappa Mentale

### 3. Download e Condivisione
- Download file in vari formati
- Invio email automatico
- Export PNG/SVG delle mappe

## 🔧 Personalizzazione

### Modifica Stili

Edita `src/App.css` per personalizzare:
- Colori e gradienti
- Animazioni
- Layout responsive

### Aggiungi Funzionalità

Estendi i servizi in `src/services/`:
- Nuovi provider AI
- Formati export aggiuntivi
- Integrazione cloud storage

### API Custom

Modifica `src/services/transcriptionService.js`:
```javascript
// Aggiungi il tuo provider preferito
async transcribeWithCustomAPI(audioBlob) {
  const response = await fetch('YOUR_API_ENDPOINT', {
    method: 'POST',
    body: formData
  });
  return response.json();
}
```

## 🐛 Troubleshooting

### Errore Microfono
- Verifica permessi browser
- Usa HTTPS in produzione
- Controlla impostazioni privacy

### Deploy Failed
```bash
# Reinstalla dipendenze
rm -rf node_modules package-lock.json
npm install

# Rebuild e deploy
npm run build
npm run deploy
```

### API Errors
- Verifica API keys in `.env`
- Controlla quote e limiti
- Usa modalità demo se necessario

## 📱 PWA (Progressive Web App)

L'app è configurata come PWA:
- **Installabile** su device mobili
- **Offline ready** per funzionalità base
- **Responsive** su tutti i dispositivi

## 🚀 Ottimizzazioni Produzione

### Performance
- Code splitting automatico
- Lazy loading componenti
- Compressione asset

### SEO
- Meta tags ottimizzati
- Sitemap automatica
- Schema.org markup

### Security
- HTTPS obbligatorio
- CSP headers
- API keys sicure

## 🔄 Aggiornamenti

Per aggiornare l'app:

```bash
git pull origin main
npm install
npm run build
npm run deploy
```

## 🤝 Contribuire

1. Fork del repository
2. Crea branch feature (`git checkout -b feature/amazing-feature`)
3. Commit modifiche (`git commit -m 'Add amazing feature'`)
4. Push al branch (`git push origin feature/amazing-feature`)
5. Apri Pull Request

## 📄 Licenza

Progetto sotto licenza MIT. Vedi `LICENSE` per dettagli.

## 🆘 Supporto

- **Issues**: [GitHub Issues](https://github.com/TUO-USERNAME/voice-transcription-app/issues)
- **Documentazione**: [Wiki](https://github.com/TUO-USERNAME/voice-transcription-app/wiki)
- **Email**: tua-email@example.com

## 🙏 Ringraziamenti

- [React](https://reactjs.org/)
- [Lucide Icons](https://lucide.dev/)
- [OpenAI API](https://openai.com/api/)
- [Markmap.js](https://markmap.js.org/)

---

**Made with ❤️ and React**

⭐ Se il progetto ti è utile, lascia una stella su GitHub!
