## Build

From the repository root, configure the Clang build:

```sh
cmake --preset clang
```

Then compile the project:

```sh
cmake --build --preset clang
```

For a Release build:

```sh
cmake --preset clang -DCMAKE_BUILD_TYPE=Release
cmake --build --preset clang
```

To compile with GCC instead of Clang, replace `clang` with `gcc`. You need to clear the `build/` folder before switching compilers.
