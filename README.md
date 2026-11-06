# Upscaler 4K

Site statique pour agrandir des images en 1080p, 2K, 4K ou à la résolution détectée de l'écran, en paysage ou en vertical (proportions conservées).

- Glisser-déposer, sélection ou collage (Ctrl+V) de plusieurs images à la fois
- Moteur rapide (Lanczos3) ou IA (ESRGAN, détails reconstruits)
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
- IA : [UpscalerJS](https://upscalerjs.com) (MIT) + [TensorFlow.js](https://www.tensorflow.org/js) (Apache-2.0), modèle ESRGAN-slim x4 (`vendor/esrgan-slim-x4/`, poids renommés en `.wasm` pour être servis partout tels quels)
- ZIP via [JSZip](https://github.com/Stuk/jszip) (`vendor/jszip.min.js`, MIT/GPLv3)
- Sortie JPEG 95 % pour les photos, PNG pour les formats pouvant contenir de la transparence
