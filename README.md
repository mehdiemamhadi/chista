# chista (چیستا)
> Named after Chista, an ancient Iranian divine figure associated with knowledge, wisdom, and insight.

Knowledge grows through curiosity, and wisdom comes with practice. Chista is my personal C++ learning repository — a place to experiment, solve problems, explore programming concepts, and improve one small program at a time. Nothing too complicated. Just learning, building, making mistakes, and getting better.

<br/>

## Getting Started
### Requirements
- A C++ compiler (MSVC, GCC, or Clang)
- CMake 4.3 or later
- A compatible IDE or code editor (Visual Studio recommended)

Chista uses **CMake** to manage independent exercises within a **single project**.

<br/>

## Project Structure
``` powershell
Chista/
├── CMakeLists.txt
└── exercises/
    ├── 01-hello-world/
    │   ├── CMakeLists.txt
    │   └── main.cpp
    └── ...
```
Each **exercise** is an **independent executable** with its own **source files** and **CMake configuration**.

<br/>

## Adding a New Exercise
Adding a new exercise is simple. Just follow these steps:

### 1. Create a new directory
Inside the `exercises/` directory, create a folder for your new **exercise**.

For example:
``` powershell
exercises/
└── 02-<your_exercise_name>/
```

### 2. Create the source file
Add a main.cpp file inside the new directory:
``` cpp
// Your new exercise code...
```

### 3. Create a CMakeLists.txt
Inside your new **exercise** directory, create a CMakeLists.txt file (`exercises/<your_exercise_name>/CMakeLists.txt`):
``` cmake
add_executable(<your_exercise_name> main.cpp) #Remove `<your_exercise_name>` and enter your exercise name.
```
For example if you enter `number_guessing`, the name **number_guessing** will be used as the executable target name.

If your exercise contains **multiple** source files, simply add them:
``` cmake
add_executable(number_guessing
    main.cpp
    game.cpp
    game_utils.cpp
)
```

### 4. Register the exercise
Open the root **CMakeLists.txt** file and add your **new exercise** using `add_subdirectory()`:
``` cmake
add_subdirectory(exercises/02-<your_exercise_name>) #Remove `<your_exercise_name>` and enter your exercise name.
```
That's it! Your new exercise is now part of the **Chista** project

<br/>

## Building the Project
### - Visual Studio
1. Open Visual Studio.
2. Select Open a local folder.
3. Open the **root Chista** directory.
4. Let CMake configure the project.
5. Select your desired exercise from the startup target list.
6. Build and run

### - Command Line
If you have **CMake** installed on your system (separate from the **version** installed with Visual Studio as part of the **C++ development** workload), you can also **configure** and **build** the project using **CMake**:
``` powershell
cmake -S . -B build
cmake --build build
```
To build a specific exercise:
``` powershell
cmake --build build --target <your_exercise_name>
```

<br/>

## License
This repository is primarily a personal learning space. Feel free to explore the code and learn from it.
