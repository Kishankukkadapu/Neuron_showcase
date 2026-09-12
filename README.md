# Neuron — project page

A one-page case study for **Neuron**, an iOS platform that teaches the modern
AI stack and runs Python entirely on-device.

Live: https://kishankukkadapu.github.io/Neuron_showcase/

This repository contains only the public page — the app's source lives in a
separate private repository.

## Structure

```
index.html        the whole page (no build step, no dependencies)
assets/icon.png   app icon
assets/shots/     screenshots, captured from the shipping build
.nojekyll         serve files as-is, don't run Jekyll
```

## Adding the demo video

Find the placeholder in `index.html` marked `<!-- Replace this block -->` and
swap it for the embed:

```html
<iframe src="https://www.youtube.com/embed/VIDEO_ID" title="Neuron demo"
        allowfullscreen loading="lazy"></iframe>
```

Record on a **physical iPhone** — the on-device model uses MLX, which cannot
run in the iOS Simulator.

## Regenerating the screenshots

Every screen is reachable by launch argument, so the set is reproducible from
the app repo without tapping through anything:

```bash
xcrun simctl launch <device> python-genie.Python-Practice \
  -onboarding.hasSeenTour YES -startTab labs -openCodeLab YES \
  -codeLabOpenProblem 2 -labCode "<code>" -labAutoRun YES
```
