project('meshoptimizer', 'cpp')
meshoptimizer_inc = ['extern','gltf','src']
meshoptimizer_lib = static_library(
    'meshoptimizer',
    [
      'src/allocator.cpp',
      'src/clusterizer.cpp',
      'src/indexanalyzer.cpp',
      'src/indexcodec.cpp',
      'src/indexgenerator.cpp',
      'src/meshletcodec.cpp',
      'src/meshletutils.cpp',
      'src/opacitymap.cpp',
      'src/overdrawoptimizer.cpp',
      'src/partition.cpp',
      'src/quantization.cpp',
      'src/rasterizer.cpp',
      'src/remesher.cpp',
      'src/simplifier.cpp',
      'src/spatialorder.cpp',
      'src/stripifier.cpp',
      'src/tangentspace.cpp',
      'src/vcacheoptimizer.cpp',
      'src/vertexcodec.cpp',
      'src/vertexfilter.cpp',
      'src/vfetchoptimizer.cpp',
      'gltf/animation.cpp',
      'gltf/encodebasis.cpp',
      'gltf/encodewebp.cpp',
      'gltf/fileio.cpp',
      'gltf/gltfpack.cpp',
      'gltf/image.cpp',
      'gltf/json.cpp',
      'gltf/material.cpp',
      'gltf/mesh.cpp',
      'gltf/node.cpp',
      'gltf/parsegltf.cpp',
      'gltf/parselib.cpp',
      'gltf/parseobj.cpp',
      'gltf/splats.cpp',
      'gltf/stream.cpp',
      'gltf/wasistubs.cpp',
      'gltf/write.cpp',
    ],
    include_directories: meshoptimizer_inc,
    override_options: ['unity=off']
)

meshoptimizer_dep = declare_dependency(
    include_directories: 'src',
    link_with: meshoptimizer_lib,
)

meson.override_dependency('meshoptimizer', meshoptimizer_dep)
