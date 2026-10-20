project('glslang', 'cpp')

sources = [
    'glslang/ResourceLimits/resource_limits_c.cpp',
    'glslang/ResourceLimits/ResourceLimits.cpp',
    'glslang/stub.cpp',
    'glslang/MachineIndependent/attribute.cpp',
    'glslang/MachineIndependent/Constant.cpp',
    'glslang/MachineIndependent/glslang_tab.cpp',
    'glslang/MachineIndependent/InfoSink.cpp',
    'glslang/MachineIndependent/Initialize.cpp',
    'glslang/MachineIndependent/Intermediate.cpp',
    'glslang/MachineIndependent/intermOut.cpp',
    'glslang/MachineIndependent/IntermTraverse.cpp',
    'glslang/MachineIndependent/iomapper.cpp',
    'glslang/MachineIndependent/limits.cpp',
    'glslang/MachineIndependent/linkValidate.cpp',
    'glslang/MachineIndependent/parseConst.cpp',
    'glslang/MachineIndependent/ParseContextBase.cpp',
    'glslang/MachineIndependent/ParseHelper.cpp',
    'glslang/MachineIndependent/PoolAlloc.cpp',
    'glslang/MachineIndependent/preprocessor/Pp.cpp',
    'glslang/MachineIndependent/preprocessor/PpTokens.cpp',
    'glslang/MachineIndependent/preprocessor/PpContext.cpp',
    'glslang/MachineIndependent/preprocessor/PpScanner.cpp',
    'glslang/MachineIndependent/preprocessor/PpAtom.cpp',
    'glslang/MachineIndependent/propagateNoContraction.cpp',
    'glslang/MachineIndependent/reflection.cpp',
    'glslang/MachineIndependent/RemoveTree.cpp',
    'glslang/MachineIndependent/Scan.cpp',
    'glslang/MachineIndependent/ShaderLang.cpp',
    'glslang/MachineIndependent/SpirvIntrinsics.cpp',
    'glslang/MachineIndependent/SymbolTable.cpp',
    'glslang/MachineIndependent/Versions.cpp',
    'glslang/CInterface/glslang_c_interface.cpp',
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
    # 'StandAlone/StandAlone.cpp',
]
glslang_args = ['-DENABLE_HLSL', '-DENABLE_SPIRV', '-DENABLE_OPT']
glslang_inc = ['.', 'glslang/Include', 'SPIRV', 'glslang/Public']
if host_machine.system() == 'windows'
    sources += 'glslang/OSDependent/Windows/ossource.cpp'
    glslang_inc += 'glslang/OSDependent/Windows'
    glslang_args += '-DGLSLANG_OSINCLUDE_WIN32'
else
    sources += 'glslang/OSDependent/Unix/ossource.cpp'
    glslang_inc += 'glslang/OSDependent/Unix'
    glslang_args += '-DGLSLANG_OSINCLUDE_WIN32'
endif

glslang_lib = static_library(
    'glslang',
    sources,
    include_directories: glslang_inc,
    cpp_args: glslang_args,
)

glslang_dep = declare_dependency(
    include_directories: ['.'],
    link_with: glslang_lib,
)

meson.override_dependency('glslang', glslang_dep)
