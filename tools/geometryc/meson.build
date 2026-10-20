geometryc_exe = executable(
'geometryc',
'geometryc.cpp',
dependencies: [dependency('bx'), dependency('bgfx'), dependency('meshoptimizer'), dependency('cgltf')]
)

meson.override_find_program('geometryc',geometryc_exe)
