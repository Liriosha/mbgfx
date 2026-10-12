project('bgfx',['c','cpp'], default_options : ['cpp_std=c++20'])

fs = import('fs')
sources = []
foreach s : fs.read('sources.txt').strip().split('\n')
    sources += files('src/' + s + '.cpp')
endforeach

bimg_dep = subproject('mbimg').get_variable('bimg_dep')
bx_dep = subproject('mbx').get_variable('bx_dep')
imgui_dep = subproject('imgui').get_variable('imgui_dep')

bgfx_inc_dirs = [
  'include',
  '3rdparty',
  '3rdparty/directx-headers/include',
  '3rdparty/directx-headers/include/directx',
  '3rdparty/khronos',
]

if host_machine.system() != 'windows'
  bgfx_inc_dirs += '3rdparty/directx-headers/include/wsl/stubs'
endif
bgfx_inc = include_directories(bgfx_inc_dirs)

bgfx_args = []

if host_machine.system() == 'linux' and get_option('with_wayland')
  bgfx_args += '-DWL_EGL_PLATFORM=1'
endif

if host_machine.system() == 'darwin'
  bgfx_args += '-xobjective-c++'
endif

bgfx_lib = static_library('bgfx', sources,
  include_directories: bgfx_inc,
  dependencies: [
    bx_dep,
    bimg_dep,
    dependency('gl')
  ],
  cpp_args : bgfx_args,
)


meshoptimizer_lib = static_library('meshoptimizer', [
    '3rdparty/meshoptimizer/src/allocator.cpp',
    '3rdparty/meshoptimizer/src/clusterizer.cpp',
    '3rdparty/meshoptimizer/src/indexanalyzer.cpp',
    '3rdparty/meshoptimizer/src/indexcodec.cpp',
    '3rdparty/meshoptimizer/src/indexgenerator.cpp',
    '3rdparty/meshoptimizer/src/overdrawoptimizer.cpp',
    '3rdparty/meshoptimizer/src/partition.cpp',
    '3rdparty/meshoptimizer/src/quantization.cpp',
    '3rdparty/meshoptimizer/src/rasterizer.cpp',
    '3rdparty/meshoptimizer/src/simplifier.cpp',
    '3rdparty/meshoptimizer/src/spatialorder.cpp',
    '3rdparty/meshoptimizer/src/stripifier.cpp',
    '3rdparty/meshoptimizer/src/vcacheoptimizer.cpp',
    '3rdparty/meshoptimizer/src/vertexcodec.cpp',
    '3rdparty/meshoptimizer/src/vertexfilter.cpp',
    '3rdparty/meshoptimizer/src/vfetchoptimizer.cpp',
  ],
)

bgfx_dep = declare_dependency(
  link_with: [
    bgfx_lib,
    meshoptimizer_lib
  ],
  dependencies: imgui_dep,
  include_directories: bgfx_inc
)
