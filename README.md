# fidestock-installateur

Dépôt public de distribution des mises à jour **FIDESTOK**.

Ce dépôt ne contient **aucun code source** (il reste privé) : uniquement les
installateurs et le manifeste `latest.json` validé par l'application.

- `latest.json` : manifeste de la dernière version (version, URL, empreinte
  SHA-256, notes, taille).
- `FIDESTOK-Setup-<version>.exe` : installeur signé par son empreinte.

Publication : `Outils\publier-maj.cmd <version>` dans le dépôt de
développement.

## Â« Windows a protÃ©gÃ© votre ordinateur Â»

L'installeur n'est pas encore signÃ© avec un certificat de code. Au premier
lancement d'un fichier tÃ©lÃ©chargÃ©, Microsoft Defender SmartScreen affiche donc
Â« Windows a protÃ©gÃ© votre ordinateur Â», et le contrÃ´le de compte d'utilisateur
annonce Â« Ã‰diteur : inconnu Â».

Ce message ne signifie pas que le fichier est altÃ©rÃ© : il signifie que Windows
ne peut pas vÃ©rifier d'oÃ¹ vient le fichier. Pour installer, cliquez
Â« Informations complÃ©mentaires Â» puis Â« ExÃ©cuter quand mÃªme Â».

### VÃ©rifier le fichier avant de l'installer

TÃ©lÃ©chargez VERIFIER-LE-FICHIER.cmd et VERIFIER-LE-FICHIER.ps1 depuis la
release, dÃ©posez-les Ã  cÃ´tÃ© du .exe, puis double-cliquez sur
VERIFIER-LE-FICHIER.cmd.

Le rÃ©sultat attendu est **FICHIER CONFORME** : l'empreinte SHA-256 calculÃ©e
correspond Ã  celle publiÃ©e dans latest.json. Le script affiche aussi la
signature du fichier (signed = Â« Ã‰diteur Â» renseignÃ©, non signÃ© = avertissement
SmartScreen attendu).

### Et pour la suite

La signature de code, qui supprimerait ce message dÃ©finitivement, n'est pas
encore en place : l'outillage est prÃªt (Outils\signer-fichier.ps1) et la
signature sera posÃ©e automatiquement avant chaque publication dÃ¨s qu'un
certificat sera disponible. D'ici lÃ , l'avertissement n'apparaÃ®t qu'une fois
par version tÃ©lÃ©chargÃ©e.
