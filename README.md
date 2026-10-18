# Memristor Model Generator / 忆阻器模型生成器

A single-file, dependency-free web tool that turns memristor model parameters into
ready-to-run LTspice `.lib` files and schematics.

一个单文件、零依赖的网页工具：选模型、填参数，直接生成可在 LTspice 里跑的
`.lib` 模型文件和原理图。

Live demo / 在线演示: https://wendy272.github.io/memristor-model-generator/

---

## Models / 内置模型

| Model | Type |
|---|---|
| Strukov linear drift (HP 2008) | ion drift |
| Vourkas 2013 | threshold tunnel barrier |
| VTEAM (Kvatinsky 2015) | threshold adaptive |
| Wang 2021 | binarized behavioral |
| Strukov + Benderli window | ion drift + window |
| Strukov + Joglekar window | ion drift + window |
| Strukov + Biolek window | ion drift + window |
| Strukov + Prodromakis window | ion drift + window |
| TEAM | current threshold |
| Ideal memristor (Chua) | charge-controlled |
| Custom | four-slot template |

## Features / 功能

- 11 built-in models / 11 个内置模型
- Chinese / English UI / 中英双语切换
- Light / dark theme / 日间、夜间模式
- Vourkas internal parameters (`fo`, `Lo`) solved automatically from RON/ROFF
- Exports a `.lib` file or a ZIP containing `.lib` + `memristor.asy` + `test_*.asc`
- No dependencies, no build step — just open `index.html`

## Usage / 用法

1. Open `index.html` (or the live demo).
2. Pick a model and set its parameters.
3. Download `.lib` or the schematic pack.
4. Extract the ZIP, open `test_<model>.asc` in LTspice.
5. Press `Alt+R`, then add trace `-I(V1)` and set the x-axis to `V(top)`.

中文：

1. 打开 `index.html`（或在线演示）。
2. 选模型、填参数。
3. 下载 `.lib` 或原理图包。
4. 解压后用 LTspice 打开 `test_模型名.asc`。
5. 按 `Alt+R`，加 `-I(V1)`，横轴选 `V(top)`。

## Notes / 说明

- Models are behavioral, not calibrated physical models.
- All generated models were tested with LTspice 26.1.1.
- The `memristor.asy` symbol must stay in the same folder as the `.asc` schematic.

## References / 参考

- Strukov et al., *The missing memristor found*, Nature 2008.
- Vourkas, Batsos, Sirakoulis, *SPICE modeling of nonlinear memristive behavior*,
  Int. J. Circ. Theor. Appl. 43:553–565, 2015.
- Kvatinsky et al., TEAM (2013) and VTEAM (2015).
- Wang et al., *A Behavioral SPICE Model of a Binarized Memristor for Digital Logic
  Implementation*, Circuits Syst. Signal Process. 40:2682–2693, 2021.
- Joglekar & Wolf (2009), Biolek et al. (2009), Prodromakis et al. (2011),
  Benderli & Wey (2009) — window functions.
- Chua, *Memristor — the missing circuit element*, IEEE CT 1971.

## Disclaimer / 免责声明

This tool is provided **for learning and teaching purposes only**. It is not intended
for commercial, production, or engineering use. The models are behavioral
approximations and do not represent all characteristics of real devices.

本工具**仅供学习与教学使用**，不用于商业、生产或任何工程决策。模型为行为级近似，
不代表真实器件的全部特性。

## License

MIT
