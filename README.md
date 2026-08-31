# MobiPass — App mobile (prototype)

Ce dossier contient le prototype MobiPass (Voyageur / Opérateur / Terminal) empaqueté avec **Capacitor** pour être compilé en APK Android via **GitHub Actions**. Vous n'avez rien à installer sur votre ordinateur.

## Étape 1 — Créer le dépôt GitHub

1. Allez sur [github.com/new](https://github.com/new)
2. Créez un dépôt (public ou privé), par exemple `mobipass-app`
3. Ne cochez aucune case d'initialisation (pas de README, pas de .gitignore — vous avez déjà les vôtres)

## Étape 2 — Envoyer les fichiers sur GitHub

**Option A — Interface web (le plus simple)**
1. Sur la page de votre nouveau dépôt, cliquez sur "uploading an existing file"
2. Glissez-déposez **tout le contenu de ce dossier** (en gardant la structure : `www/`, `.github/`, `package.json`, etc.)
3. Cliquez sur "Commit changes"

**Option B — Ligne de commande**
```bash
cd mobipass-app
git init
git add .
git commit -m "Premier commit MobiPass"
git branch -M main
git remote add origin https://github.com/VOTRE-NOM/mobipass-app.git
git push -u origin main
```

## Étape 3 — Récupérer l'APK

1. Sur GitHub, allez dans l'onglet **Actions** de votre dépôt
2. Vous verrez un workflow "Build APK" en cours d'exécution (environ 3-5 minutes)
3. Une fois terminé (coche verte ✓), cliquez dessus
4. En bas de la page, section "Artifacts", téléchargez **mobipass-debug-apk**
5. C'est un fichier `.zip` — dézippez-le pour obtenir `app-debug.apk`

## Étape 4 — Installer l'APK sur votre téléphone

1. Transférez `app-debug.apk` sur votre téléphone Android (par email, WhatsApp, ou câble USB)
2. Ouvrez le fichier — Android demandera l'autorisation d'installer des applications inconnues, acceptez
3. L'application MobiPass s'installe et s'ouvre normalement

## Structure du projet

```
mobipass-app/
├── www/
│   └── index.html          → le contenu de l'application (les 3 vues)
├── .github/workflows/
│   └── build-apk.yml       → compile automatiquement l'APK à chaque push
├── package.json            → dépendances Capacitor
├── capacitor.config.json   → configuration de l'app (nom, id, dossier web)
└── .gitignore
```

## Pour modifier l'application

Tout le contenu visuel et fonctionnel se trouve dans `www/index.html`. Modifiez ce fichier, poussez sur GitHub (`git push`), et une nouvelle APK sera générée automatiquement.

## Remarque importante

Ceci est un **APK de debug** (non signé pour le Play Store), parfait pour tester l'application sur un téléphone. Pour publier sur le Google Play Store, il faudra générer une APK/AAB signée — on pourra voir cette étape plus tard si vous en avez besoin.
