# MemoCookSwift — Legal Pages

Ce repo est la **source unique de vérité** pour les pages légales de l'app MemoCookSwift.

Les fichiers HTML sont servis via **GitHub Pages** à l'adresse :
`https://klimae29.github.io/MemoCookSwift-privacy/`

## Pages disponibles

| Page | URL |
|------|-----|
| Politique de confidentialité | [`/privacy-policy.html`](https://klimae29.github.io/MemoCookSwift-privacy/privacy-policy.html) |
| Conditions d'utilisation | [`/terms.html`](https://klimae29.github.io/MemoCookSwift-privacy/terms.html) |
| Support | [`/support.html`](https://klimae29.github.io/MemoCookSwift-privacy/support.html) |

## Architecture

L'app charge ces pages **en priorité depuis GitHub Pages** (version toujours à jour).
En cas d'absence de réseau, elle bascule automatiquement sur la copie embarquée dans le bundle.

```
En ligne  → https://klimae29.github.io/MemoCookSwift-privacy/<fichier>.html
Hors ligne → Bundle.main (Legal/<fichier>.html)
```

## ⚠️ Workflow de mise à jour

Lors de toute modification d'un fichier légal :

1. **Modifier** le fichier HTML dans ce repo → commit/push → GitHub Pages se met à jour automatiquement
2. **Copier** le même fichier dans `MemoCookSwift/Legal/` (app Xcode) → commit/push → fallback offline à jour

> Ne modifier qu'un seul endroit cassera soit la version en ligne, soit le fallback offline.
