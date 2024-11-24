# clang-18.wasm

## Build
### Emscripten
emsdk-3.1.69
### LLVM
release-18.x
### ninja
1.12.1
### cmake
3.30.3
### command
```bat
@REM cwd:llvm-project
mkdir build_ninja
cd build_ninja
emcmake cmake -G Ninja -DLLVM_ENABLE_PROJECTS="clang;lld" -DCMAKE_BUILD_TYPE=MinSizeRel -DLLVM_INCLUDE_TESTS=OFF -DLLVM_INCLUDE_BENCHMARKS=OFF -DLLVM_INCLUDE_EXAMPLES=OFF -DLLVM_HOST_TRIPLE=wasm32-unknown-emscripten -DLLVM_TARGETS_TO_BUILD="ARM;X86;AArch64;RISCV;WebAssembly" -DCMAKE_CXX_FLAGS="-sWASM_BIGINT -sALLOW_MEMORY_GROWTH -sALLOW_TABLE_GROWTH" ../llvm
```

## Info
Arch support:`ARM`;`X86`;`AArch64`;`RISCV`;`WebAssembly`

Enable projects:`clang`;`lld`

## How to ues
Who knows!(I want to create an online tool for compiling elf/pe file)

# Good Luck
