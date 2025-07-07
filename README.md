# Atlas-Action_Component

This is a Module for atlas engine. It allows us to create action components quickly and similarly.

---

## Setup

### 1. Snippets

Place the snippet file in your project's `.vscode` folder.

### 2. Module Folder

Place the folder in `modules/`.

---

## To Make a Modules Package

### Step 1: Create a `modules` folder in your project.

```
your_project/
├── modules/
│   └── atlas-action_component/
```

### Step 2: Create a `modules.cmake` file in `modules/`.

```cmake
file(GLOB_RECURSE MODULE_SOURCES
    CONFIGURE_DEPENDS
    ${CMAKE_CURRENT_LIST_DIR}/*/*.cpp
    ${CMAKE_CURRENT_LIST_DIR}/*/*.hpp
)

set(MODULE_SOURCES ${MODULE_SOURCES} PARENT_SCOPE)
```

### Step 3: Update your `CMakeLists.txt`.

Add this line near the top or where appropriate:

```cmake
include(${CMAKE_CURRENT_LIST_DIR}/modules/modules.cmake)
```

Then, inside your `build_application(...)` call, add `MODULE_SOURCES`:

```cmake
build_application(
    SOURCES
    ...
    ${MODULE_SOURCES}
    ...
)
```

---

You're done!
