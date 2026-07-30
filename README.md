# Valorant AI Meta Suggester

AI tool that reads a match loading screen and gives strategy suggestions based on the map and comps.

## How it works

1. Screenshot the loading screen (ShareX)
2. CV pipeline pulls out the match data:
   - Agent classifier (fine-tuned ResNet18) reads all 10 agents from splash art
   - Map OCR (Tesseract) reads the map name
3. RAG pipeline retrieves relevant strategies and generates set plays for the comp
4. Electron app ties it all together

## Status

- ✅ Crop pipeline (works across resolutions)
- ✅ Map OCR — validated on every map tested so far
- ✅ Agent classifier — 97% test accuracy, 29 classes (still collecting more data)
- 🚧 RAG / strategy generation
- 🚧 Electron app

## Notebook

[Comp Classifier Pipeline (Colab)](https://colab.research.google.com/drive/1IKL6GMTZxq0vMj1Ti1l3Mbn5HDtclEf1?usp=sharing)

## Tracking

See [Issues](../../issues) for tasks, split by workstream (classifier / RAG / Electron) under linked epics.

## Original brainstorm

Started from two ideas:
- **Meta Suggester**: suggest comps + set plays from loading screen data
- **Minimap Tracker**: suggest gameplans from comp, map, round history, and playstyle (future)

Notes:
- Overlays like this don't get flagged by Valorant anti-cheat (same as Valorant Tracker, overlay clip tools)
- Similar open-source projects exist for map/agent meta suggestions, used as inspo not directly reused
