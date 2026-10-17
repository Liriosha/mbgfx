project('glslang','cpp')

sources = [
'glslang/ResourceLimits/resource_limits_c.cpp',
'glslang/ResourceLimits/ResourceLimits.cpp',
'glslang/stub.cpp',
'glslang/CInterface/glslang_c_interface.cpp',
'glslang/MachineIndependent/ParseContextBase.cpp',
'glslang/MachineIndependent/reflection.cpp',
'glslang/MachineIndependent/attribute.cpp',
'glslang/MachineIndependent/Intermediate.cpp',
'glslang/MachineIndependent/IntermTraverse.cpp',
'glslang/MachineIndependent/propagateNoContraction.cpp',
'glslang/MachineIndependent/RemoveTree.cpp',
'glslang/MachineIndependent/linkValidate.cpp',
'glslang/MachineIndependent/SymbolTable.cpp',
'glslang/MachineIndependent/Constant.cpp',
'glslang/MachineIndependent/intermOut.cpp',
'glslang/MachineIndependent/Scan.cpp',
'glslang/MachineIndependent/parseConst.cpp',
'glslang/MachineIndependent/ShaderLang.cpp',
'glslang/MachineIndependent/iomapper.cpp',
'glslang/MachineIndependent/Versions.cpp',
'glslang/MachineIndependent/ParseHelper.cpp',
'glslang/MachineIndependent/SpirvIntrinsics.cpp',
'glslang/MachineIndependent/InfoSink.cpp',
'glslang/MachineIndependent/limits.cpp',
'glslang/MachineIndependent/preprocessor/Pp.cpp',
'glslang/MachineIndependent/preprocessor/PpTokens.cpp',
'glslang/MachineIndependent/preprocessor/PpContext.cpp',
'glslang/MachineIndependent/preprocessor/PpScanner.cpp',
'glslang/MachineIndependent/preprocessor/PpAtom.cpp',
'glslang/MachineIndependent/glslang_tab.cpp',
'glslang/MachineIndependent/PoolAlloc.cpp',
'glslang/MachineIndependent/Initialize.cpp',
'glslang/HLSL/hlslTokenStream.cpp',
'glslang/HLSL/hlslParseHelper.cpp',
'glslang/HLSL/hlslAttributes.cpp',
'glslang/HLSL/hlslScanContext.cpp',
'glslang/HLSL/hlslOpMap.cpp',
'glslang/HLSL/hlslParseables.cpp',
'glslang/HLSL/hlslGrammar.cpp',
'glslang/GenericCodeGen/CodeGen.cpp',
'glslang/GenericCodeGen/Link.cpp',
'SPIRV/SpvTools.cpp',
'SPIRV/SpvBuilder.cpp',
'SPIRV/disassemble.cpp',
'SPIRV/SpvPostProcess.cpp',
'SPIRV/Logger.cpp',
'SPIRV/CInterface/spirv_c_interface.cpp',
'SPIRV/InReadableOrder.cpp',
'SPIRV/doc.cpp',
'SPIRV/GlslangToSpv.cpp',
'StandAlone/StandAlone.cpp',
]

if host_machine.system() == 'windows'
  sources += 'glslang/OSDependent/Windows/ossource.cpp';
else
  sources += 'glslang/OSDependent/Unix/ossource.cpp'
endif

glslang_lib = static_library(
    'glslang',
    sources,
    include_directories: ['glslang/include'],
)

glslang_dep = declare_dependency(
    include_directories: ['glslang/include'],
    link_with: glslang_lib
)

meson.override_dependency('glslang', glslang_dep)
