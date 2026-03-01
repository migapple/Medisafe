# MediSafe — Setup Capacitor

## Structure des fichiers

```
medisafe/
├── www/
│   └── index.html        ← Ton fichier HTML (fourni)
├── package.json          ← Fourni
├── capacitor.config.json ← Fourni
└── ios/                  ← Généré par Capacitor
    └── App/
        └── App/
            └── public/   ← Copie auto de www/
```

---

## 1. Installer les dépendances

```bash
npm install
```

---

## 2. Ajouter la plateforme iOS

```bash
npx cap add ios
```

---

## 3. Copier www/ → ios/App/App/public/

```bash
npx cap sync ios
```

---

## 4. Ouvrir dans Xcode

```bash
npx cap open ios
```

---

## 5. Dans Xcode — Permission caméra (Info.plist)

Ajoute cette clé dans Info.plist :

- Clé   : NSCameraUsageDescription
- Valeur : MediSafe utilise la caméra pour scanner les codes-barres des médicaments.

---

## ⚡ Workflow au quotidien

Quand tu modifies index.html dans www/ :

```bash
npx cap sync ios
# puis ⌘R dans Xcode
```

**NE JAMAIS** éditer les fichiers dans ios/App/App/public/ — ils sont écrasés à chaque sync.

---

## 📋 Rappel structure Bundle ID

- App ID    : com.garlandat.medisafe
- App Name  : MediSafe
- Version   : 1.0.0

Modifie l'App ID dans capacitor.config.json si besoin.
