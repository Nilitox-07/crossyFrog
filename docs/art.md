# Procedural Obstacle And Art System Plan

## Goal

Build a procedural obstacle and art system where gameplay objects are defined by their grid footprint, such as `1x1`, `1x2`, `3x1`, or up to `12x12`, and art assets can be randomly or dynamically selected to match that footprint.

The key idea is to separate gameplay behavior from visual appearance. An obstacle knows how much space it occupies and how it behaves. The art system knows which sprites can visually represent that obstacle size.

## Core Concept

Everything should be measured in grid units first, not pixels.

Examples:

- `1x1`: small rock, bush, cone, coin, frog-sized obstacle
- `2x1`: short log, small car, crate stack
- `3x1`: long log, car, bench, hedge
- `1x2`: vertical sign, tall post, stacked object
- `4x2`: truck, wide platform, large hazard
- `12x12`: large set piece, arena-sized decoration, major terrain feature

Pixel size should be derived from the tile size. For example, if one tile is `64px`, then a `3x1` obstacle renders at `192px x 64px`.
