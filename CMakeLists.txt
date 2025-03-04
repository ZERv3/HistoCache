cmake_minimum_required(VERSION 3.10)  # Минимальная версия CMake
project(MyProject CXX)  # Название проекта

set(CMAKE_CXX_STANDARD 20)  # Используем C++ 20
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Собираем список всех .cpp файлов (исключаем .h)
set(SOURCE_FILES
    main.cpp
    Tests/TestsCache.cpp
    Tests/LoadTestsCache.cpp
    Tests/DictionaryTests.cpp
    Histogram/Histogram.cpp
)

# Добавляем исполняемый файл (только с .cpp-файлами)
add_executable(MyProject ${SOURCE_FILES})

# Указываем, где искать заголовочные файлы
target_include_directories(MyProject PRIVATE
    Tests
    Sorting
    Sequences
    ObjectClasses
    Interface
    Histogram
    Hash
    Cache
)

# Опционально: включаем предупреждения компилятора
target_compile_options(MyProject PRIVATE -Wall -Wextra -Wpedantic)
