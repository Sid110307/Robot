# Robot

> Making an agent learn how to move (with PyTorch).

## Getting Started

### Prerequisites

- A compiler that supports C++20 or later ([GCC](https://gcc.gnu.org/), [Clang](https://clang.llvm.org/), etc.).
- [CMake](https://cmake.org/) 3.2 or later.
- [OpenGL](https://www.opengl.org/) 4.3 or later.
- [GLFW](https://www.glfw.org/).
- [GLEW](http://glew.sourceforge.net/).
- [GLM](https://github.com/g-truc/glm.git).
- [PyTorch (libtorch)](https://pytorch.org/).

### Installation

- Clone the repository

```bash
$ git clone https://github.com/Sid110307/Robot.git
$ cd Robot
```

- Configure and build the project

```bash
$ cmake -S . -B bin
$ cmake --build bin --target all -j4
```

- Run the executable

```bash
$ ./bin/robot
```

## License

[MIT](https://opensource.org/licenses/MIT)

