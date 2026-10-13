<div align="center">

# Zariep Software

**Game development, Research and tooling for shipping [raylib-d](https://github.com/schveiguy/raylib-d) games:**

![Linux](https://img.shields.io/badge/Linux-fc9f24?style=flat-square&logo=linux&logoColor=fff) ![Windows](https://img.shields.io/badge/Windows-3daee9.svg?style=flat-square&&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAABZ0lEQVRYR+2XXUoDQRCEHf+CCoLig9GI/z/xEJ7GY3gDX71NchGfAr6K+uBTQF2/gg6skmSnpaMgs1B0IMtUbfXu9FSam/FVVdUCFDtgHxyBY8MZ9SFF8EOyzDobRiSSc3Bp9ZS6CpbGcPWyBUCyyAIroAPuwRW4tqfZo27a/55n+ioAEgnaBbLnEBzUIBJZ+aqaUhpyf+VhG+sAa9waiQhl13rDos/RArxP8f8EfGBp9svIvS+gHfkOFAHvWDrv+JzCW1AEvGG/BkbuFd6CWQiob27Tfvc933+uQ677/l4Aw8jbgidNTOdOOGne9NMvCZjUll4R8BMHws8D3pewCCgOhDtwwy5xApRodCzfbtjMY6fhdzJ2RuWCLlCGU1YYZTpVBZNh6KE0d3RZyGyZQwNmgYLRnYmUe1tA+dBztsjPhtOEWqRbMxGKcGqp2nkBFFTlnsQrX9avGAFNLiJQ5Aq1wqi1qo+fh6soaLcWDXQAAAAASUVORK5CYII=) ![Android](https://img.shields.io/badge/Android-A4C639?style=flat-square&logo=android&logoColor=fff) ![Web](https://img.shields.io/badge/Web%2FWASM-654FF0?style=flat-square&logo=webassembly&logoColor=fff)

![D](https://img.shields.io/badge/D%2FBetterC-B63838?style=flat-square&logo=d&logoColor=fff)
![LDC](https://img.shields.io/badge/LDC%2FLLVM-262D3A?style=flat-square&logo=llvm&logoColor=fff) 
![Raylib](https://img.shields.io/badge/Raylib-000000?style=flat-square&logo=raylib&logoColor=fff) 

</div>

---

## About

This research explore how far a game written in D with raylib-d can travel. The focus is practical: documenting what works, what breaks and why, then packaging the working parts into reusable templates.

Everything here is built around one stack:

- **Language:** D, compiled in `-betterC` mode
- **Compiler:** [LDC](https://github.com/ldc-developers/ldc) (LLVM-based)
- **Library:** [raylib](https://github.com/raysan5/raylib) through [raylib-d](https://github.com/schveiguy/raylib-d)
- **Host:** Linux (the only host tested so far)

## Featured projects

### 📱 [raylib-d-android-template](https://github.com/Zariep-Software/raylib-d-android-template)

A template and Git submodule for building raylib-d games for Android. A native D script (`build-android.d`) builds `libmain.so` per ABI.

### 🔬 [raylib-d-crossbuild-research](https://github.com/Zariep-Software/raylib-d-crossbuild-research)

Research notes on compiling raylib-d games for Linux, Windows, Android and WebAssembly using LDC and `-betterC`. It covers design decisions, required toolchains, directory layout, per-platform steps, a troubleshooting table and open questions.


## Key findings

- **`-betterC` is strongly recommended.** The D runtime and GC cause serious problems on Android and WASM, and GC pauses suit frame-sensitive game code poorly. The trade-off is no GC, classes, exceptions or druntime-dependent features.
- **LDC is the compiler of choice** thanks to LLVM's broad platform support and better `-betterC` handling. DMD and GDC are not covered.



## Contributing

Found a failure on a device, host or toolchain version we haven't covered? Open an issue or pull request on the relevant repository. Reproducible reports on untested platforms are especially welcome.

## Related projects

- [raylib](https://github.com/raysan5/raylib): the C library underneath it all
- [raylib-d](https://github.com/schveiguy/raylib-d): D bindings for raylib
- [LDC](https://github.com/ldc-developers/ldc): the LLVM D compiler
