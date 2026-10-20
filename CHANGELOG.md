# Changelog

All notable changes to this package are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.0] - 2026-10-21

### Added

- Initial UPM package split from the SPECTER//TICK game repository (`SpecterTick.Core` / `SpecterTick.Core.Tests` assemblies).
- Grid puzzle session (`GridPuzzleEngineSession`), game state, recorded command sequence, and stage layout snapshot.
- Stage definition model, validation (`StageValidator`), and validated stage type.
- Switches, doors, and activated-switch tracking for cooperative puzzle logic.
- EditMode tests and stage fixture builders (F1, F2, F2N, F2R) used by engine and validation tests.
- `Retry()` on the engine session and determinism/retry test coverage.
