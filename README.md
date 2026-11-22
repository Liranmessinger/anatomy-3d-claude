# Anatomy 3D – Interactive Human Body Atlas

An interactive 3D encyclopedia of the human body that runs entirely in the browser. Explore organs and body systems, run a live heart and lung simulation, follow guided journeys through the body, learn about common medical conditions, and test yourself with a quiz. Available in **Hebrew (RTL)** and **English**.

> **Educational use only.** This project is for general learning and is not a substitute for professional medical advice, diagnosis or treatment. In an emergency, call your local emergency number (101 in Israel, 911 in the US).

## Features

- **3D body model** – rotate, zoom and pan. Click any organ to see what it is, what it does, its embryonic origin (ectoderm, mesoderm or endoderm) and a "Did you know?" fact.
- **11 body systems, 55 organs** – skin, skeletal, muscular, circulatory, respiratory, digestive, nervous, urinary, endocrine, immune/lymphatic and reproductive. Each system can be switched on and off, and organs can be found with search.
- **Female / male toggle** – shows the matching reproductive organs and adjusts the body shape slightly.
- **Detail levels** – Beginner, High school and Advanced. Higher levels add deeper explanations for major organs and harder quiz questions.
- **Live simulation** – beating heart, breathing lungs and flowing blood. Choose sleep, rest, walk, run or panic and watch heart rate and breathing react.
- **Journeys** – step-by-step guided trips through the body: a bite of food, a red blood cell, the route of the blood, an oxygen molecule, a sip of water, a nerve reflex, an adrenaline rush, a sound and a ray of light.
- **Conditions** – what happens inside the body in heart attack, cardiac arrest, stroke, flu, asthma attack, diabetes, kidney stone, broken bone, severe allergic reaction and high blood pressure. Affected organs glow red, vitals change with each step, and each condition lists warning signs, what to do and prevention.
- **Quiz** – 10 questions per round: find the organ on the model, identify it from a clue, name its system, and (at higher levels) its role or embryonic origin. Includes score and streaks.
- **Narration** – read any explanation aloud using the browser's built-in speech. A header button turns on auto-narration, and every explanation has its own play/stop button.
- **Auto-play** – journeys and conditions can advance on their own: each step is narrated, then moves to the next step 2 seconds after the narration ends.
- **Learn section** – a short guide from cell to body, the systems, embryonic development and facts.
- **6 themes** – Light, Dark, Ocean, Rose, Forest and Ember.
- **Responsive** – works on desktop and mobile (panels become bottom sheets).

## Getting started

There is no build step and no backend. The whole app is one HTML file.

1. Download or clone the repository.
2. Open `index.html` (or `human-body-3d.html`) in a modern browser (Chrome, Edge, Firefox or Safari).

The 3D engine ([Three.js](https://threejs.org/) r128) is loaded from the cdnjs CDN, so an internet connection is needed the first time. To run fully offline, download `three.min.js` (r128), place it next to the HTML file and change the script tag:

```html
<script src="three.min.js"></script>
```

## Controls

| Action | Mouse | Touch |
| --- | --- | --- |
| Rotate | Drag | One finger |
| Zoom | Scroll wheel | Pinch |
| Pan | Shift + drag, or right-drag | – |
| Select organ | Click | Tap |

## Deploying

Because it is a static site, any static host works: GitHub Pages, Netlify, Cloudflare Pages or Vercel.

**GitHub Pages**

1. Rename `human-body-3d.html` to `index.html`.
2. Push to a GitHub repository.
3. In the repository, go to *Settings → Pages*, choose the main branch and the root folder, and save.
4. Your site will be available at `https://<username>.github.io/<repository>/`.

**Netlify Drop** – drag the folder onto <https://app.netlify.com/drop>.

## Narration notes

Narration uses the browser's Web Speech API, so there is no server, API key or cost. The available voices depend on the device and browser:

- **Microsoft Edge** offers natural Hebrew and English voices and gives the best results.
- Other browsers may not include a Hebrew voice. If none is found, the app shows a message, and auto-play still advances using a timer based on text length.

## Tech stack

- Plain HTML, CSS and JavaScript (single file, no framework)
- [Three.js](https://threejs.org/) r128 for 3D rendering
- Web Speech API for narration
- `localStorage` to remember language, theme, detail level and narration preferences (no data leaves the device)

## Project structure

```
.
├── index.html     # The entire app (markup, styles, data and logic)
└── README.md
```

Inside the file, the script is organised in sections: data (systems, organs, journeys, conditions), English and Hebrew strings, the 3D scene and organ geometry, picking and camera controls, the UI, quiz, narration and initialisation.

## Customising and extending

- **Add an organ** – add an entry in the organ data, add its English text, then add its 3D shape in the scene section.
- **Add a journey or condition** – add an object with its steps to `JOURNEYS` or `CONDS`. Each step names the organs to highlight and has Hebrew and English text.
- **Add a language** – add a new string table next to `STR.he` and `STR.en`, plus translations for organ, system, journey and condition text.
- **Add a theme** – add a palette to the `THEMES` object.

## Content and accuracy

The medical and biological text is written for a general audience. If you publish this publicly, have a qualified professional review it, especially the first-aid guidance in the Conditions section.

## Credits and licence

- 3D engine: [Three.js](https://github.com/mrdoob/three.js) (MIT licence).
- The organ models are simplified shapes generated in code, so there are no external model or image assets.
- Choose a licence for your own code and add a `LICENSE` file (for example MIT) before publishing.
