cmake_minimum_required(VERSION 3.10)

project(ShapesLibrary)

# ��� ��������������� �������� ���� �������� �� DLL
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

# ��������� ����������
add_library(Shapes SHARED
    lib/Shape.cpp
    lib/Triangle.cpp
    lib/Quadrangle.cpp
    lib/RightTriangle.cpp
    lib/IsoscelesTriangle.cpp
    lib/EquilateralTriangle.cpp
    lib/Rectangle.cpp
    lib/Square.cpp
    lib/Parallelogram.cpp
    lib/Rhombus.cpp
)

# ��������� ���������� � ������������� �������
target_include_directories(Shapes PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

# ������� ����������� ����
add_executable(ShapesApp src/main.cpp)

# ��������� ���������� � �����������
target_link_libraries(ShapesApp Shapes)
