# Pense Bem

A simulator of the Tectoy Pense Bem, the Brazilian educational toy from the
early 1990s, as a web page (JavaScript + SVG). Fork of
[lpereira/Pense-Bem](https://github.com/lpereira/Pense-Bem).

## Run it with Nix

```bash
nix run github:felipelalli/Pense-Bem
```

This opens the simulator in the default browser. To install it, add the flake as
an input (NixOS or home-manager) and install `packages.<system>.default`. That
gives you the `pensebem` command, a "Pense Bem" menu entry and an icon.

## What this fork changes

- **The book activity (LIVRO) works again.** Upstream's last commit left the
  answer keys uncomputed, so the keyboard locked up after the first answer. The
  keys are now computed in JavaScript and match every answer in `SAMPLES`
  (99 books × 150 questions). Scoring and the rejection of book 00 are fixed too.
- **Nix packaging** in `flake.nix` and `nix/`. The page is built without the
  Makefile's Python 2, Closure Compiler, cpp and PHP steps; `nix/package.nix`
  explains how.

The simulator, its artwork and the research notes (`FINDINGS`, `SAMPLES`,
`calcanswer.py`) are upstream's.
