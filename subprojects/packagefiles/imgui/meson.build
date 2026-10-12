project('imgui','cpp')
imgui_lib = static_library('imgui',[
    'imgui_demo.cpp',
    'imgui_draw.cpp',
    'imgui_tables.cpp',
    'imgui_widgets.cpp',
    'imgui.cpp'
  ],
  include_directories: '.',
)
imgui_dep = declare_dependency(include_directories: '.', link_with: imgui_lib)
meson.override_dependency('imgui', imgui_dep)
