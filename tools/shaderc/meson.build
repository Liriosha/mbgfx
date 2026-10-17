inc_dirs = [
  '../../include',
  '../../3rdparty',
  '../../3rdparty/khronos',
]

dep_names = [
  'spirv-cross',
  'spirv-headers',
  'spirv-tools',
  'bx',
  'bimg',
  'meshoptimizer',
  'glslang',
  'directx-headers'
]
deps = []
foreach n : dep_names
    deps += dependency(n)
endforeach
args = []
if get_option('shaderc-glslang')
  args +='-DSHADERC_CONFIG_HAS_GLSLANG' 
endif
if get_option('shaderc-tint')
  args += '-DSHADERC_CONFIG__HAS_TINT'
endif
if get_option('shaderc-d3d')
  args += '-DSHADERC_CONFIG_HAS_D3DCOMPILER'

if host_machine.system() != 'windows'
  deps += dependency('d3d4linux')
endif

endif
cc = meson.get_compiler('cpp')
deps += cc.find_library(
    'glslang-default-resource-limits',
    required : false,
)

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
dependencies: deps,
include_directories: inc_dirs,
cpp_args: args,
override_options: ['unity=off']
)

meson.override_find_program('shaderc',shaderc_exe)
