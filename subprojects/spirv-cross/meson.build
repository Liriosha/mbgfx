project('spirv-cross', 'cpp')

spirvcross_lib = static_library(
    'spirv-cross',
    [
        'spirv_cfg.cpp',
        'spirv_cpp.cpp',
        'spirv_cpp.hpp',
        'spirv_cross_c.cpp',
        'spirv_cross.cpp',
        'spirv_cross_parsed_ir.cpp',
        'spirv_cross_util.cpp',
        'spirv_glsl.cpp',
        'spirv_hlsl.cpp',
        'spirv_msl.cpp',
        'spirv_parser.cpp',
        'spirv_reflect.cpp',
    ],
    include_directories: ['include'],
)

spirvcross_dep = declare_dependency(
    include_directories: ['include', '.'],
    link_with: spirvcross_lib,
)

meson.override_dependency('spirv-cross', spirvcross_dep)
