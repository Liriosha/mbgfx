inc_dirs = [
  '../../include',
  '../../3rdparty',
  '../../3rdparty/directx-headers/include',
  '../../3rdparty/directx-headers/include/directx',
  '../../3rdparty/khronos',
  '../../3rdparty/glslang'
]

if host_machine.system() != 'windows'
  inc_dirs += '../../3rdparty/directx-headers/include/wsl/stubs'
endif

shaderc_exe = executable(
'shaderc',
[
'pp.cpp',
'shaderc.cpp',
'shaderc_dxil.cpp',
'shaderc_glsl.cpp',
'shaderc_hlsl.cpp',
'shaderc_metal.cpp',
'shaderc_pssl.cpp',
'shaderc_spirv.cpp',
'shaderc_wgsl.cpp',
'../../src/shader.cpp',
'../../src/vertexlayout.cpp'
],
dependencies: [dependency('meshoptimizer'),dependency('bx'),dependency('bimg')],
include_directories: inc_dirs,
)

meson.override_find_program('shaderc',shaderc_exe)
