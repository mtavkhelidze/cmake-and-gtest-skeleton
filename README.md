# A skeleton CMake C++ library project with Google Test support

## Setup

To start your own project

- clone this repository

```bash
$ git clone git@github.com:mtavkhelidze/cmake-and-gtest-skeleton.git
```

- set your own `origin`

```bash
$ git remote set-url origin the_url_of_your_repo_here
$ git push -u origin master
```

- add/remove files in `src/CMakeList.txt`, develop, commit, and push as normal

## Build

### Debug and Test

```bash
$ mkdir -p build
$ cd build
$ cmake -DCMAKE_BUILD_TYPE=Debug ../
$ cmake --build .
$ ctest
```

To see Google Tests' verbose output, do
```bash
$ ctest -V
```

## Release

```bash
$ mkdir -p build
$ cd build
$ cmake -DCMAKE_BUILD_TYPE=Release ../
$ cmake --build .
```

## Install

```bash
$ cd build
$ cmake --build . --clean-first --target install
```
