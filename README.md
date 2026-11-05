# SPECTER//TICK Core (`com.yuya_hatano.specter-tick-core`)

ゲーム本体 [SpecterTick](https://github.com/yuya-hatano-abs/SpecterTick) 用の **Unity 非依存**ロジック（記録・再生・スイッチ/ドア・ステージ検証）UPM パッケージです。  
[SpecterTick](https://github.com/yuya-hatano-abs/SpecterTick) とあわせ、**AI 協働開発の実験**の一部として公開しています（役割分担はゲーム側 [README](https://github.com/yuya-hatano-abs/SpecterTick#ai協働開発について) を参照）。

Unity-independent grid puzzle core for **SPECTER//TICK**: command recording and playback, switches and doors, stage validation, and EditMode unit tests.

## Install (local path)

Place this repository as a sibling of your game project (for example `../SpecterTick.Core` next to `SpecterTick`), then add to the game's `Packages/manifest.json`:

```json
"com.yuya_hatano.specter-tick-core": "file:../../SpecterTick.Core"
```

Adjust the `file:` path relative to the game's `Packages/` folder if your layout differs.

## Install (Git URL)

```json
"com.yuya_hatano.specter-tick-core": "https://github.com/yuya-hatano-abs/SpecterTick.Core.git#v0.1.1"
```

Git URL install is not verified in this repository; validate in your environment before relying on it.

## testables

The consuming project must list this package under `testables` in `Packages/manifest.json` so EditMode tests in the package appear in the Unity Test Runner:

```json
"testables": [
  "com.yuya_hatano.specter-tick-core"
]
```

## Running tests

1. Open the consuming project in Unity (Unity **6000.3** or newer; tested with 6000.3.26f1).
2. Open **Window > General > Test Runner**.
3. Select **EditMode** and run assembly `SpecterTick.Core.Tests`.

Command line example:

```text
Unity.exe -batchmode -nographics -projectPath "<path-to-project>" -runTests -testPlatform EditMode -assemblyNames SpecterTick.Core.Tests -testResults "<path-to-results.xml>" -logFile "<path-to-log>"
```

The host project should include `com.unity.test-framework`; this package does not declare it in `package.json` dependencies.

## Known constraints

- Do not keep a copy of Core under `Assets/` and this package at the same time; assembly definition names would conflict.
- New Unity `.meta` files for `package.json`, documentation, and new folders must be generated in the Editor and committed with the package.
- Package tests depend on Unity Test Framework assemblies supplied by the host project.
