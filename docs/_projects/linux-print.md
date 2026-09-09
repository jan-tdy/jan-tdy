---
title: "Linux Print"
image: /assets/projects/linux-print.png
order: 6
---
🖨️ A PyQt6 print manager for Ubuntu/Kubuntu and any modern CUPS-based distro — USB, network and remote-CUPS-server printers with autodiscovery, that keeps working after a printer's IP address or port changes.

Built because the usual Linux printing complaint isn't CUPS itself — it's that a printer silently breaks the moment its address changes, with no clue why. Linux Print is a front-end for CUPS plus a background watcher that keeps re-discovering printers and fixes their device URI when it drifts.

- **Printers tab** — live status, connection type, add/remove/enable/set default.
- **Plotter tab** — Silhouette Cameo cutting plotters: SVG/PNG/PDF import, freehand drawing, roll-fed vinyl, print-and-cut.
- **Booklet tab** — turns a PDF into a saddle-stitched A5 booklet, printed 2-up on A4.

**Repository:** [jan-tdy/linux-print](https://github.com/jan-tdy/linux-print)
