# clang-18.wasm

## 构建

### Emscripten
版本：emsdk-3.1.69

### LLVM
分支：release-18.x

### ninja
版本：1.12.1

### cmake
版本：3.30.3

### 命令
```bat
@REM 当前目录：llvm-project
mkdir build_ninja
cd build_ninja
emcmake cmake -G Ninja -DLLVM_ENABLE_PROJECTS="clang;lld" -DCMAKE_BUILD_TYPE=MinSizeRel -DLLVM_INCLUDE_TESTS=OFF -DLLVM_INCLUDE_BENCHMARKS=OFF -DLLVM_INCLUDE_EXAMPLES=OFF -DLLVM_HOST_TRIPLE=wasm32-unknown-emscripten -DLLVM_TARGETS_TO_BUILD="ARM;X86;AArch64;RISCV;WebAssembly" -DCMAKE_CXX_FLAGS="-sWASM_BIGINT -sALLOW_MEMORY_GROWTH -sALLOW_TABLE_GROWTH" ../llvm
```

## 信息
支持的架构：`ARM`; `X86`; `AArch64`; `RISCV`; `WebAssembly`

启用的项目：`clang`; `lld`

## 补丁
本补丁未在本项目应用，在安卓sdk28+环境下定义resourceDir可以使用补丁来间接支持定义。

## 如何使用
谁知道呢！（我想创建一个在线工具用于编译 ELF/PE 文件）

*clang*:`.c` -> `.o`

*lld*: `.o` - > `bin`

有一些已知问题，如果让clang自动使用lld一步到位，那就需要彻底想办法搞一个合适的文件系统和配套工具，以及这么一堆东西我一时无从下手……

# 祝你好运
