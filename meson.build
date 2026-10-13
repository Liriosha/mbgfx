project('bgfx',['c','cpp'], default_options : ['cpp_std=c++20','unity=on'])

if host_machine.system() == 'Linux'
  add_project_arguments('-fPIC', language: 'cpp')
endif


fs = import('fs')
sources = []
foreach s : fs.read('sources.txt').strip().split('\n')
    sources += files('src/' + s + '.cpp')
endforeach

bimg_dep = subproject('mbimg').get_variable('bimg_dep')
bx_dep = subproject('mbx').get_variable('bx_dep')

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

bgfx_dep = declare_dependency(
  link_with: [
    bgfx_lib,
  ],
  include_directories: bgfx_inc
)
