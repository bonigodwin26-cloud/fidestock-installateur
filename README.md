# fidestock-installateur

Dépôt public de distribution des mises à jour **FIDESTOK**.

Ce dépôt ne contient **aucun code source** (il reste privé) : uniquement les
installateurs et le manifeste `latest.json` validé par l'application.

- `latest.json` : manifeste de la dernière version (version, URL, empreinte
  SHA-256, notes, taille).
- `FIDESTOK-Setup-<version>.exe` : installeur signé par son empreinte.

Publication : `Outils\publier-maj.cmd <version>` dans le dépôt de
développement.