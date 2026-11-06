# Upscaler 4K

Site statique pour agrandir des images en 4K en 1080p, 2K, 4K ou à la résolution détectée de l'écran, en paysage ou en vertical (proportions conservées).

- Glisser-déposer, sélection ou collage (Ctrl+V) de plusieurs images à la fois
- Traitement par lot automatique avec progression
- Téléchargement image par image ou de tout le lot en un seul ZIP
- 100 % dans le navigateur : aucune image n'est envoyée sur un serveur

## Lancer

Ouvrir `index.html`, ou servir le dossier :

```sh
python3 -m http.server 8000   # puis http://localhost:8000
```

Déployable tel quel sur GitHub Pages, Netlify, etc.

## Technique

- Redimensionnement Lanczos3 + accentuation via [pica](https://github.com/nodeca/pica) (`vendor/pica.min.js`, MIT)
- ZIP via [JSZip](https://github.com/Stuk/jszip) (`vendor/jszip.min.js`, MIT/GPLv3)
- Sortie JPEG 95 % pour les photos, PNG pour les formats pouvant contenir de la transparence
