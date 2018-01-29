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

- develop, commit, and push as normal

## Compiling & Running Tests

```bash
$ mkdir build
$ cd build
$ cmake ../
$ make && make test
```

To see Google Tests' verbose output, do
```bash
$ make test ARGS="-V" 
```
