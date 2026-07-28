# v0.2.0 Tag Checklist

Use this before cutting the v0.2.0 public tag.

## Required Checks

```sh
zig fmt build.zig bench/main.zig src/*.zig test_support/*.zig
zig build test
zig build
zig build -Doptimize=ReleaseFast bench
zig build run -- --synthetic gradient --width 16 --height 4 --mode density --color none
zig build run -- --input testdata/diagonal.ppm --width 1 --height 1 --mode partition --partition quadrant --color none
```

## Release Notes

- Semantic Mermaid rendering for flowcharts, sequences, state, class, ER, C4,
  architecture, card, and mindmap diagrams.
- Shared `CellCanvas` terminal drawing substrate.
- Sextant and octant sub-cell image partitions.
- Floyd-Steinberg dithering and ANSI 16/256-color output.
- Real-font headless visual review with `glyphshot`.
- Automated quality corpus and visual-gallery tooling.

## Pre-Tag Review

- Confirm `build.zig.zon` version.
- Confirm `CHANGELOG.md` has the intended v0.2.0 section.
- Confirm no decoder is exported from `src/root.zig`.
- Confirm benchmark numbers are refreshed or explicitly marked as historical.
- Confirm GitHub remote is correct.

## Tag Commands

```sh
git tag -a v0.2.0 -m "v0.2.0"
git push origin main
git push origin v0.2.0
```
