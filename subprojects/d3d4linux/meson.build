project('d3d4linux','cpp')

d3d4linux_lib = static_library(
    'd3d4linux',
    'd3d4linux.cpp',
    include_directories: ['include'],
    dependencies: [dependency('directx-headers')],
)

d3d4linux_dep = declare_dependency(
    include_directories: ['include'],
    link_with: d3d4linux_lib,
)

meson.override_dependency('d3d4linux', d3d4linux_dep)
